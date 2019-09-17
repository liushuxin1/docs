 # 服务间Feign相互调用
 
 使用场景：A服务要调用B服务的方法
> 1、在接口上使用@Inside注解（如：SysLogController.save方法）

    /**
     * 插入日志
     *
     * @param sysLog 日志实体
     * @return
     */
    @Inside
    @PostMapping("/save")
    public R save(@Valid @RequestBody SysLog sysLog) {
        return R.ok(sysLogService.save(sysLog));
    }
    
    
>2、编写Feign接口（如：RemoteLogService）
    
    /**
     * 保存日志
     *
     * @param sysLog 日志实体
     * @param from   是否内部调用
     * @return succes、false
     */
    @PostMapping("/log/save")
    R<Boolean> saveLog(@RequestBody SysLog sysLog, @RequestHeader(SecurityConstants.FROM) String from);
    
>3、调用接口（如：SysLogListener）
    
    @Async
    @Order
    @EventListener(SysLogEvent.class)
    public void saveSysLog(SysLogEvent event) {
        SysLog sysLog = event.getSysLog();
        remoteLogService.saveLog(sysLog, SecurityConstants.FROM_IN);
    }