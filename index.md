## ROYALCMS框架介绍

Royalcms框架是由一个具有多年行业开发经验的iOS工程师设计、研发的一套适用于模块化开发的网站平台系统，您可以瞬间完成一个模块，展示您的创意。五层架构封装，让每一层都可以独立扩展，不受影响。

### 官方QQ群：84329252

## Royalcms开发框架功能亮点：

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

	.															根目录
	├── content										功能模块目录
	│   ├── apps									应用模块目录
	│   │   ├── achievement				
	│   │   ├── adsense
	│   │   ├── affiliate
	│   │   ├── api
	│   │   ├── article
	│   │   ├── bonus
	│   │   ├── captcha
	│   │   ├── cart
	│   │   ├── client
	│   │   ├── comment
	│   │   ├── connect
	│   │   ├── coupon
	│   │   ├── cycleimage
	│   │   ├── database
	│   │   ├── dscapi
	│   │   ├── favourable
	│   │   ├── feedback
	│   │   ├── gongyun
	│   │   ├── goods
	│   │   ├── groupbuy
	│   │   ├── installer
	│   │   ├── integrate
	│   │   ├── logviewer
	│   │   ├── mail
	│   │   ├── main
	│   │   ├── maintain
	│   │   ├── merchant
	│   │   ├── mobile
	│   │   ├── orders
	│   │   ├── payment
	│   │   ├── promotion
	│   │   ├── push
	│   │   ├── seller
	│   │   ├── setting
	│   │   ├── shipping
	│   │   ├── sms
	│   │   ├── topic
	│   │   ├── toutiao
	│   │   ├── user
	│   │   └── visual
	│   ├── bootstrap						启动入口文件
	│   │   ├── autoload.php
	│   │   ├── cache
	│   │   ├── classalias.php
	│   │   ├── classmap.php
	│   │   ├── console.php
	│   │   ├── kernel.php
	│   │   └── royalcms.php
	│   ├── configs							配置文件
	│   │   ├── api.php
	│   │   ├── bundles.php
	│   │   ├── cache.php
	│   │   ├── command
	│   │   ├── compile.php
	│   │   ├── console.php
	│   │   ├── cookie.php
	│   │   ├── coreservice.php
	│   │   ├── database.php
	│   │   ├── ecjia.php
	│   │   ├── facade.php
	│   │   ├── filesystems.php
	│   │   ├── logging.php
	│   │   ├── mail.php
	│   │   ├── multisites.php
	│   │   ├── namespaces.php
	│   │   ├── packages
	│   │   ├── provider.php
	│   │   ├── queue.php
	│   │   ├── release.php
	│   │   ├── route.php
	│   │   ├── session.php
	│   │   ├── site.php
	│   │   ├── storage.php
	│   │   ├── system.php
	│   │   └── upload.php
	│   ├── database							数据迁移文件
	│   │   └── migrations
	│   ├── kernel								内核文件
	│   │   ├── Console
	│   │   ├── Exceptions
	│   │   └── Http
	│   ├── plugins								插件目录
	│   │   ├── captcha_royalcms
	│   │   ├── login_mobile
	│   │   ├── pay_alipay
	│   │   ├── pay_balance
	│   │   ├── pay_bank
	│   │   ├── pay_bill24
	│   │   ├── pay_cash
	│   │   ├── pay_cod
	│   │   ├── pay_koolyun
	│   │   ├── pay_koolyun_alipay
	│   │   ├── pay_koolyun_unionpay
	│   │   ├── pay_koolyun_upmp
	│   │   ├── pay_koolyun_wxpay
	│   │   ├── pay_upmp
	│   │   ├── pay_wxpay
	│   │   ├── pay_wxpay_wap
	│   │   ├── ship_cac
	│   │   ├── ship_ems
	│   │   ├── ship_post_express
	│   │   ├── ship_post_mail
	│   │   ├── ship_presswork
	│   │   ├── ship_sf_express
	│   │   ├── ship_sto_express
	│   │   ├── ship_yto
	│   │   ├── ship_yunda
	│   │   ├── ship_zto
	│   │   ├── sms_ecjia
	│   │   ├── sms_ihuyi
	│   │   ├── sms_ihuyi_global
	│   │   ├── sms_messagebird
	│   │   ├── ucenter
	│   │   └── ueditor
	│   ├── resources							资源目录
	│   │   └── components
	│   ├── routes								路由目录
	│   │   ├── bootstrap.php
	│   │   ├── command.php
	│   │   ├── global.php
	│   │   ├── local.php
	│   │   └── routes.php
	│   ├── system								管理后台目录
	│   │   ├── apis
	│   │   ├── classes
	│   │   ├── configs
	│   │   ├── database
	│   │   ├── functions
	│   │   ├── languages
	│   │   ├── model
	│   │   ├── smarty
	│   │   ├── statics
	│   │   └── templates
	│   ├── tests									测试用例目录
	│   │   ├── ApiTest
	│   │   ├── Bootstrap.php
	│   │   ├── CreatesApplication.php
	│   │   ├── ExampleTest.php
	│   │   ├── Feature
	│   │   ├── FrameworkTest
	│   │   ├── TestCase.php
	│   │   └── Unit
	│   └── uploads								附件上传目录
	│       └── data
	├── sites											多站点目录
	│   ├── admincp								管理后台入口
	│   │   └── index.php
	│   ├── api										API站点
	│   │   ├── content
	│   │   ├── index.php
	│   │   └── notify
	│   ├── app										APP站点
	│   │   ├── content
	│   │   └── index.php
	│   ├── cron									计划任务站点
	│   │   ├── content
	│   │   ├── ecjia							命令行工具
	│   │   ├── index.php			
	│   │   └── vendor
	│   └── testapi								API测试工具
	│       ├── content
	│       └── index.php
	├── vendor  									框架目录
	├── index.php									入口文件
	├── phpunit.php								单元测试入口
	├── phpunit.xml								单元测试配置文件



**[5.x 版本文档看](docs/5.x/index.md)**



## ROYALCMS 核心组件

- royalcms/auth
- royalcms/broadcasting
- royalcms/bus
- royalcms/cache
- royalcms/class-loader
- royalcms/config
- royalcms/console
- royalcms/contracts
- royalcms/cookie
- royalcms/database
- royalcms/encryption
- royalcms/events
- royalcms/exception
- royalcms/filesystem
- royalcms/foundation
- royalcms/hashing
- royalcms/http
- royalcms/log
- royalcms/mail
- royalcms/notifications
- royalcms/pagination
- royalcms/pipeline
- royalcms/preloader
- royalcms/queue
- royalcms/redis
- royalcms/routing
- royalcms/session
- royalcms/support
- royalcms/translation
- royalcms/validation
- royalcms/view

## 相关组件
- [royalcms/metable](/docs/metable/index)
- [royalcms/enum](/docs/enum/index)
- royalcms/agent
- royalcms/aliyun
- royalcms/api
- royalcms/app
- royalcms/convert
- royalcms/datetime
- royalcms/default-route
- royalcms/directory-hasher
- royalcms/editor
- royalcms/elasticsearch
- royalcms/enum
- royalcms/environment
- royalcms/error
- royalcms/excel
- royalcms/gettext
- royalcms/hook
- royalcms/http-request
- royalcms/ide-helper
- royalcms/image
- royalcms/image-editor
- royalcms/ip-address
- royalcms/kses
- royalcms/log-viewer
- royalcms/memcache
- royalcms/model
- royalcms/native-session
- royalcms/pacage
- royalcms/page
- royalcms/pay
- royalcms/pinyin
- royalcms/plugin
- royalcms/purifier
- royalcms/qrcode
- royalcms/reflection
- royalcms/rememberable
- royalcms/repository
- royalcms/requests
- royalcms/rewrite
- royalcms/script
- royalcms/sentry
- royalcms/service
- royalcms/smarty-view
- royalcms/sms
- royalcms/storage
- royalcms/temporary-directory
- royalcms/theme
- royalcms/timer
- royalcms/upload
- royalcms/uploader
- royalcms/url
- royalcms/uuid
- royalcms/variable
- royalcms/widget
- royalcms/xml-response
