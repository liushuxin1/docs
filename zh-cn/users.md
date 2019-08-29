# 多租户功能

        多租户功能是基于租户共享同一个Database、同一个Schema，但在表中通过tenant_id区分租户的数据的模式，基于mybatis-plus的多租户SQL解析器实现

>租户功能说明

    自动维护租户ID，不需要手动处理，即可实现通过租户ID 过滤的效果
    表中预留 tenant_id 字段
    在配置中心维护这张表即可（base-weixin-mp-dev.yml）

>租户表维护

    base:
      tenant:
        column: tenant_id
        tables:
          - wx_app
          - wx_menu
          - wx_user
          - wx_auto_reply
          - wx_msg
          - wx_mass_msg
          
>通过前端传递的token，获取当前用户的租户ID

>全局拦截器拦截传递的token在redis中获取到租户ID 放到theadlocal 中
（joolun\base-common\base-common-data\src\main\java\com\joolun\cloud\common\data\tenant
\TenantContextHolderFilter.java）

>强制切换租户

    TenantContextHolder.setTenantId 即可

>注：在增删改过程中请勿对 tenant_id字段手动赋值，不然报错

>租户表维护

    部门表sys_dept中parent_id为0的部门默认为一个租户

>不需要租户信息约束的sql
在mapper的方法上添加注解@SqlParser(filter=true)

    @SqlParser(filter=true)
    SysUser getByNoTenant(SysUser sysUser);