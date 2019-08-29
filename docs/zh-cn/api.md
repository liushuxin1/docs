# 接口直接对外暴露

    用户请求时会被spring security oauth 拦截，如果没有合法token直接会被拒绝，
    如果某些接口不需要token校验
    直接在对应微服务模块配置ignore-urls: 如：base-weixin-mp-dev.yml
    
>spring security 配置

    security:
      oauth2:
        client:
          client-id: gen
          client-secret: gen
          scope: server
          # 默认放行url,子模块重写时application-dev.yml中的公共配置会被覆盖,所以要把公共配置中的放行url再写一次
          ignore-urls:
            - '/portal/**'
            - '/wxmaterial/materialFileUpload'
            - '/wxmaterial/newsImgUpload'
            - '/ws/**'
            - '/open/notify/**'
            - '/open/auth/**'