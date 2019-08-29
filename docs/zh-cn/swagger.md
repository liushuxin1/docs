 # Swagger文档配置

## 快速使用
 >在pom.xml中引入
    
        <dependency>
            <groupId>com.joolun</groupId>
            <artifactId>base-common-swagger</artifactId>
        </dependency>
>启动类中增加@BaseEnableSwagger注解

    @BaseEnableSwagger
    @SpringCloudApplication
    @EnableBaseFeignClients
    @EnableBaseResourceServer
    public class BaseWxMpApplication {
    
        public static void main(String[] args) {
            SpringApplication.run(BaseWxMpApplication.class, args);
        }
    }
    
>个性化的配置（application-dev.yml）
 ## Swagger相关的配置
    swagger:
      标题,默认空
      title: 'JooLun Swagger API'
      描述,默认空
      description: 'JooLun微信快速开发框架'
      版本,默认空
      version: '2.1.6'
      许可证,默认空
      license: 'Powered By JooLun'
      许可证URL,默认空
      licenseUrl: 'http://www.joolun.com'
      服务条款URL,默认空
      terms-of-service-url: 'http://www.joolun.com'
      文档的host信息，默认：空
      host: 'http://www.joolun.com'
      swagger会解析的包路径,默认为空，扫描所有包
      base-package: '' 
      swagger会解析的url规则
      base-path: /**
      在basePath基础上需要排除的url规则
      exclude-path: 
        - /actuator/**
        - /error  
      联系人相关配置
      contact:
         联系人姓名，默认空
        name: 'JL'
         联系人Email，默认空
        email: 'joolun@gmail.com'
         联系人URL，默认空
        url: 'http://www.joolun.com'
       统一鉴权相关配置
      authorization:
         鉴权策略名称，默认空
        name: 'JooLun OAuth'
         需要开启鉴权URL的正则，默认匹配所有
        auth-regex: '^.*$'
         鉴权作用域列表配置,默认空
        authorization-scope-list:
             鉴权作用域名称,默认空
          - scope: 'server'
             鉴权作用域描述,默认空
            description: 'server all'
         校验token的地址列表,默认空  
        token-url-list:
          - 'http://localhost:9999/auth/oauth/token'
     文档地址：http://localhost:9999/doc.html 
 参考：https://doc.xiaominfo.com/guide/