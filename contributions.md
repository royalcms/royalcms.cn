# royalcms 源代码贡献指南

- [错误反馈](#bug-reports)
- [核心开发讨论](#core-development-discussion)
- [选择分支？](#which-branch)
- [安全漏洞](#security-vulnerabilities)
- [编码风格](#coding-style)
    - [PHPDoc](#phpdoc)
    - [StyleCI](#styleci)


<a name="bug-reports"></a>
## 错误反馈

为了鼓励积极协作，royalcms 强烈地鼓励使用 Pull Request 指出修改的内容，而不仅仅只是反馈错误。「错误反馈」也可以用 PR 来提交失败测试。

如果你要提交错误反馈，你的问题应该包含标题和明确的问题描述，并尽可能多的提供相关的信息和演示该问题的代码示例。错误反馈的目的是让你和其他人可以轻松地重现并修复错误。

请记住，错误反馈的初衷是让其它有相同问题的人能够和你协作解决问题。不要指望反馈错误后会很快有人修复它。创建错误反馈是能帮助你和其他人开始着手修复问题的途径。



<a name="core-development-discussion"></a>
## 核心开发讨论

如果你想提出现有的 royalcms 的功能建议或者改进，请到 royalcms-guide 的 [反馈栏](https://github.com/royalcms/royalcms-guide/issues) 讨论。如果你提出新功能，如果愿意，我们希望能请你至少实现一些完成该功能所需的代码。


<a name="which-branch"></a>
## 选择分支？

**所有**错误修复都应该发送到最新的稳定分支上。错误修复**不**应该发送到 `master` 支，除非它们修复仅在即将发布的版本中存在的功能。

与当前 royalcms 版本**完全向后兼容**的**次要**功能可能会发送到最新的稳定分支。

**主要的** 新功能都应该发送到 `master` 分支，它包含即将发布的 royalcms 版本。


<a name="security-vulnerabilities"></a>
## 安全漏洞

如果你发现 royalcms 存在安全漏洞，请发送电子邮件给royalwang： <a href="mailto:royalwang@royalcms.cn">royalwang@royalcms.cn。他会及时解决所有安全漏洞。</a>


<a name="phpdoc"></a>
### PHPDoc

以下是正确的 royalcms 注释的示例。请注意，`@param` 属性后跟两个空格、参数类型、两个空格，最后是变量名称：

    /**
      * Filters an HTTP status header.
      *
      * @since 2.2.0
      *
      * @param string $status_header HTTP status header.
      * @param int    $code          HTTP status code.
      * @param string $description   Description for the status code.
      * @param string $protocol      Server protocol.
      */
      $status_header = RC_Hook::apply_filters( 'status_header', $status_header, $code, $description, $protocol );


<a name="styleci"></a>
### StyleCI

别担心你的编码风格不够漂亮！在合并 PR 后 [StyleCI](https://styleci.io) 会自动修正样式后再合并到 royalcms 仓库中。这样使得我们可以专注于贡献内容本身而不是编码风格。


> 文档永久地址： http://royalcms.cn/


