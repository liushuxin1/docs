# 项目结构说明
   ## 后端结构
        joolun
        ├── base-auth -- 授权服务
        ├── base-common -- 系统公共模块 
        ├    ├── base-common-parent -- 公共版本控制
        ├    ├── base-common-core -- 公共工具类包
        ├    ├── base-common-data -- 数据包
        ├    ├── base-common-log -- 日志
        ├    └── base-common-security -- 安全工具类
        ├    └── base-common-swagger -- Swagger文档
        ├── base-nacos -- ali注册中心、配置中心
        ├── base-gateway -- Spring Cloud Gateway网关
        ├── base-upms -- 后台管理模块
        ├    └── base-upms-common -- 后台管理公共模块
        ├    └── base-upms-admin -- 后台管理业务处理模块
        └── base-weixin  -- 微信模块 
             ├── base-weixin-common -- 微信公共模块
             ├── base-weixin-mp -- 微信公众号模块
     
   ## 前端结构
        joolun-ui  -- UI主目录
        ├── public -- 静态资源
        ├    └── cdn -- CDN
        ├    └── img -- 图片资源
        ├    └── svg -- SVG资源
        ├    └── util -- 工具
        ├    └── favicon.ico -- 图标
        ├    └── index.html -- 首页
        ├── src -- 源码目录 
        ├    └── api -- 后端交互的接口
        ├    ├── components -- 封装的组件
        ├    ├── config -- 放配置
        ├    ├── const -- 放常量
        ├    ├── filters -- 过滤器
        ├    └── mixins -- mixins混入
        ├    └── page -- 页面组件
        ├    └── route -- VUE路由
        ├         └── page -- 页面路由
        ├         └── views -- 业务路由
        ├         └── avue-router.js --avue路由处理，包括路由拦截，动态路由等
        ├         └── axios.js --axios增强
        ├         └── route.js --路由入口
        ├    └── store -- VUEX
        ├    └── styles -- 样式
        ├    └── util -- 工具包
        ├    └── views -- 业务上的vue页面
        ├    └── App.vue -- 根组件
        ├    └── error.js -- 错误日志处理
        ├    └── main.js -- 入口js
        ├    └── permission.js -- 权限判断
        ├── .browserslistrc -- barbel兼容配置
        ├── .editorconfig -- 开发组统一环境配置
        ├── .editorconfig -- ESLint配置
        ├── .gitignore -- git忽略
        ├── .postcssrc.js -- CSS预处理配置
        ├── babel.config.js -- barbel配置入口
        ├── package.json -- 依赖管理
        ├── vue.config.js -- vue cli3的webpack配置