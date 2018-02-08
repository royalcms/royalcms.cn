## ROYALCMS框架介绍

Royalcms框架是由一个具有多年行业开发经验的iOS工程师设计、研发的一套适用于模块化开发的网站平台系统，您可以瞬间完成一个模块，展示您的创意。五层架构封装，让每一层都可以独立扩展，不受影响。

### Royalcms开发框架功能亮点：

1. 100%开源，没有任何加密文件

	Royalcms核心文件100%开源，没有任何加密文件，开发者可以放心使用而无需担心留有后门程序等。

2. 功能组件化封装，每一个功能都是独立的

	核心组件功能独立，十分利于开发者迅速阅读掌握调用。

3. 代码严谨，结构清晰

	Royalcms使用MVC开发模式，各个功能模块之间独立并目录结构统一。开发者可迅速掌握Royalcms的框架结构。

4. 二次开发文档十分完善

	我们提供了完善的Royalcms二次开发文档，便于开发者学习与查阅。

5. 高度集成微信接口

	Royalcms高度集成了微信公共号的自动回复、菜单管理、素材管理、模板消息、粉丝管理、微信支付等常用接口，您只需一个函数或2/3行代码即可实现原本需要很费时费力才能开发的功能。

6. 高度封装常用开发功能

	只需一两行固定的代码，您便可以写出列表分页、微信支付、文件上传、邮件发送、短信发送等功能。

7. 数据结构合理，负载强劲

	Royalcms集成了常见的内存级缓存（Memcache、Redis）、文件缓存处理方案，使得系统更符合大数据、大并发的公共号或网站使用。

8. 集成应用市场，功能拓展一瞬间

	Royalcms集成了应用市场并在线安装应用的功能，您可以在一瞬间安装完成其他开发者开发的功能模块。

### Royalcms 目录结构：

	content 	功能模块目录
	verdons  	框架目录
	index.php	入口文件


## ROYALCMS框架手册

- ## 入门指南
    - [安装](/docs/{{version}}/installation)
    - [配置信息](/docs/{{version}}/configuration)
    - [文件夹结构](/docs/{{version}}/structure)    
    - [部署](/docs/{{version}}/deployment)
- ## 核心架构
    - [请求周期](/docs/{{version}}/lifecycle)
    - [服务容器](/docs/{{version}}/container)
    - [服务提供者](/docs/{{version}}/providers)
    - [Facades](/docs/{{version}}/facades)
    - [Contracts](/docs/{{version}}/contracts)
- ## 基础功能
    - [路由](/docs/{{version}}/routing)
    - [中间件](/docs/{{version}}/middleware)
    - [CSRF 保护](/docs/{{version}}/csrf)
    - [控制器](/docs/{{version}}/controllers)
    - [请求](/docs/{{version}}/requests)
    - [响应](/docs/{{version}}/responses)
    - [视图](/docs/{{version}}/views)
    - [URL](/docs/{{version}}/urls)
    - [Session](/docs/{{version}}/session)
    - [表单验证](/docs/{{version}}/validation)
    - [错误与日志](/docs/{{version}}/errors)
- ## 前端开发
    - [Blade 模板](/docs/{{version}}/blade)
    - [本地化](/docs/{{version}}/localization)
    - [前端指南](/docs/{{version}}/frontend)
    - [编辑资源 Mix](/docs/{{version}}/mix)
- ## 安全相关
    - [用户认证](/docs/{{version}}/authentication)
    - [API 认证](/docs/{{version}}/passport)
    - [用户授权](/docs/{{version}}/authorization)
    - [加密解密](/docs/{{version}}/encryption)
    - [哈希](/docs/{{version}}/hashing)
    - [重置密码](/docs/{{version}}/passwords)
- ## 综合话题
    - [Artisan 命令行](/docs/{{version}}/artisan)
    - [广播系统](/docs/{{version}}/broadcasting)
    - [缓存系统](/docs/{{version}}/cache)
    - [集合](/docs/{{version}}/collections)
    - [事件系统](/docs/{{version}}/events)
    - [文件存储](/docs/{{version}}/filesystem)
    - [辅助函数](/docs/{{version}}/helpers)
    - [邮件发送](/docs/{{version}}/mail)
    - [消息通知](/docs/{{version}}/notifications)
    - [扩展包开发](/docs/{{version}}/packages)
    - [队列](/docs/{{version}}/queues)
    - [任务调度](/docs/{{version}}/scheduling)
- ## 数据库
    - [快速入门](/docs/{{version}}/database)
    - [查询构造器](/docs/{{version}}/queries)
    - [分页](/docs/{{version}}/pagination)
    - [数据库迁移](/docs/{{version}}/migrations)
    - [数据填充](/docs/{{version}}/seeding)
    - [Redis](/docs/{{version}}/redis)
- ## Eloquent ORM
    - [快速入门](/docs/{{version}}/eloquent)
    - [模型关联](/docs/{{version}}/eloquent-relationships)
    - [Eloquent 集合](/docs/{{version}}/eloquent-collections)
    - [修改器](/docs/{{version}}/eloquent-mutators)
    - [API 资源](/docs/{{version}}/eloquent-resources)
    - [序列化](/docs/{{version}}/eloquent-serialization)
- ## 测试相关
    - [快速入门](/docs/{{version}}/testing)
    - [HTTP 测试](/docs/{{version}}/http-tests)
    - [浏览器测试 Dusk](/docs/{{version}}/dusk)
    - [数据库测试](/docs/{{version}}/database-testing)
    - [测试模拟器](/docs/{{version}}/mocking)
