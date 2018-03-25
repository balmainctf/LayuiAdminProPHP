# LayuiAdminProPHP
## LayuiAdminProPHP是针对LayuiAdminPro后台模板（以下简称LayAdmin）使用ThinkPHP5.0+开发的基础版本
## 此项目期望在基于ThinkPHP5.0+版本框架下编写一套（包含以下通用方案）的功能框架，以可以在大部分新目开始之初可拿来就用无需重复编写下方列出的功能模块提升开发效率。</br>
 + 1、账户登录、注册、密码找
 + 2、遵循 JWT（JSON Web Token）标准的鉴权方案（使用Redis），这里主要是针对单页面应用、APP后台
 + 3、LayAdmin菜单方案
 + 4、权限验证方案（完善中）
 + 5、数据缓存方案</br>
 + 6、WEB IM方案
 + 7、日志系统
 + 8、微信开发基础方案（包括、微信公众接入、自动回复、自定义菜单、微信登录、微信支付完善中  完善中）
 + 9、支付方案（包括、支付宝、微信  完善中）
 + 10、验证码方案（邮箱验证、手机验证  完善中）
 + 11、基础的系统监控、异步任务处理方案（完善中）等
 + 12、简单的shadowsocksr数据库版本的系统后台管理（用户、结点、套餐、账号监控）</br>
 + 目前就这些后续再进行完善</br>
 
等一个项目开始之初送需要基础功能方案。
## 如果你对LayAdmin、ThinkPHP5还不太了解请阅读下面的简单介绍：
 + 1、layuiAdmin后台模板介绍：
     + layuiAdmin后台模板为基于layui开发的单页面应用，所有操作无需跳转、采用前后端分离开发模式、更友好的交互体验，减轻浏览器负载、始终基于全新的 layui 版本、面向全屏幕尺寸的响应式适配能力、灵活的主题色配置。这里的基础版本目前只对单页面应用版本（layuiAdmin）进行适配<a href="http://www.layui.com/admin/">layuiAdmin官网</a>
 + 2、ThinkPHP5介绍：
     + ThinkPHP V5.0是一个为API开发而设计的高性能框架——是一个颠覆和重构版本，采用全新的架构思想，引入了很多的PHP新特性，优化了核心，减少了依赖，实现了真正的惰性加载，支持composer，并针对API开发做了大量的优化。 ThinkPHP5是一个全新的里程碑版本，包括路由、日志、异常、模型、数据库、模板引擎和验证等模块都已经重构，但绝对是新项目的首选（无论是WEB还是API开发）。<a href="http://www.thinkphp.cn/">ThinkPHP官网</a>
 ## 运行环境的简单介绍：
 + 1、推荐PHP7+版本+MySQL+Nginx
 + 2、功能模块中大量运用到Redis
 ## 目录结构简介：
 
 ~~~
www  WEB部署目录（或者子目录）
├─admin           系统后台应用目录
├─client          用户前台应用目录
├─home            用户前台入口
├─public          系统后台入口
├─extend          主要功能类目录
│  ├─custom             获取公共信息来
│  │  ├─TerminalInfo.php      获取web客户端信息类（包括ip信息）
│  ├─heillog        日志系列
│  │  ├─ErrorLog.php    系统日志写入类
│  │  ├─SsrUserLog.php   SSR操作用户记录日志写入类
│  ├─menu        菜单系列
│  │  ├─AdminMenu.php    系统后台菜单
│  │  ├─AppMenu.php      用户前台菜单
│  ├─redis        redis系列
│  │  ├─RedisLogin.php    redis登录类
│  │  ├─RedisModel.php    redis基类
│  ├─Safety        密码、验证、JWT系列、数据加密等相关
│  │  ├─Safetylogin.php   密码、验证、JWT系列、数据加密等相关
│  ├─SendMail        阿里云邮件类
│  │  ├─EmailLog.php    邮件日志类
│  │  ├─SendMail.php    初始化邮件发送类
│  │  ├─Mail.php        邮件发送方法类
│  ├─VerifiController        用以被控制器继承的权限验证、登录验证、基本信息获取
│  │  ├─AdminLoginVerifi.php    系统后台
│  │  ├─UserLoginVerifi.php     用户前台
├─table.sql        表结构
├─config.js        LayAdmin的配置
注意：这里在\thinkphp\library\think\log\driver目录下增加MysqFile.php驱动类使用MySQL记录系统错误日志（可在应用的config.php中修改）
~~~
 ## 配置简介：
 + 应用的配置都在应用目录下的config.php中，具体的直接打开config.php文件就可以了解。
 + LayAdmin的配置在根目录下config.js中
 ## 注意：
 + 由于LayAdmin需要授权故不在此上次代码[授权地址](http://www.layui.com/admin/)  
 + 由于使用了ThinkPHP5.0+框架请先了解熟悉ThinkPHP的使用[手册地址](https://www.kancloud.cn/manual/thinkphp5/118003)  
 