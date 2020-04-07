 ECJiaWiki:Ecjia后台RC Notification使用说明

#### 目录

 [隐藏] 

- [1简介](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E7.AE.80.E4.BB.8B)
- [2创建通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.88.9B.E5.BB.BA.E9.80.9A.E7.9F.A5)
- 3发送通知
  - [3.1使用 Notification Facade](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E4.BD.BF.E7.94.A8_Notification_Facade)
  - [3.2指定发送频道](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.8C.87.E5.AE.9A.E5.8F.91.E9.80.81.E9.A2.91.E9.81.93)
  - [3.3队列化通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E9.98.9F.E5.88.97.E5.8C.96.E9.80.9A.E7.9F.A5)
  - [3.4按需通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.8C.89.E9.9C.80.E9.80.9A.E7.9F.A5)
- 4邮件通知
  - [4.1格式化邮件消息](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96.E9.82.AE.E4.BB.B6.E6.B6.88.E6.81.AF)
  - [4.2其他通知格式选项](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.85.B6.E4.BB.96.E9.80.9A.E7.9F.A5.E6.A0.BC.E5.BC.8F.E9.80.89.E9.A1.B9)
  - [4.3错误消息](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF)
  - [4.4自定义接收者](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E6.8E.A5.E6.94.B6.E8.80.85)
  - [4.5自定义主题](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E4.B8.BB.E9.A2.98)
  - [4.6自定义模板](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E6.A8.A1.E6.9D.BF)
- 5Markdown 邮件通知
  - [5.1生成消息](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E7.94.9F.E6.88.90.E6.B6.88.E6.81.AF)
  - [5.2写消息](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.86.99.E6.B6.88.E6.81.AF)
  - [5.3按钮组件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.8C.89.E9.92.AE.E7.BB.84.E4.BB.B6)
  - [5.4面板组件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E9.9D.A2.E6.9D.BF.E7.BB.84.E4.BB.B6)
  - [5.5表格组件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.A1.A8.E6.A0.BC.E7.BB.84.E4.BB.B6)
  - [5.6自定义组件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E7.BB.84.E4.BB.B6)
  - [5.7自定义CSS](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89CSS)
- 6数据库通知
  - [6.1先决条件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.85.88.E5.86.B3.E6.9D.A1.E4.BB.B6)
  - [6.2格式化数据库通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96.E6.95.B0.E6.8D.AE.E5.BA.93.E9.80.9A.E7.9F.A5)
  - [6.3访问通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.AE.BF.E9.97.AE.E9.80.9A.E7.9F.A5)
  - [6.4标为已读](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.87.E4.B8.BA.E5.B7.B2.E8.AF.BB)
- 7广播通知
  - [7.1先决条件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.85.88.E5.86.B3.E6.9D.A1.E4.BB.B6_2)
  - [7.2格式化广播通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96.E5.B9.BF.E6.92.AD.E9.80.9A.E7.9F.A5)
  - [7.3广播队列配置](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.B9.BF.E6.92.AD.E9.98.9F.E5.88.97.E9.85.8D.E7.BD.AE)
  - [7.4监听通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E7.9B.91.E5.90.AC.E9.80.9A.E7.9F.A5)
  - [7.5自定义通知通道](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E9.80.9A.E7.9F.A5.E9.80.9A.E9.81.93)
- 8短信通知
  - [8.1先决条件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.85.88.E5.86.B3.E6.9D.A1.E4.BB.B6_3)
  - [8.2格式化短信通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96.E7.9F.AD.E4.BF.A1.E9.80.9A.E7.9F.A5)
  - [8.3Unicode 内容](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#Unicode_.E5.86.85.E5.AE.B9)
  - [8.4自定义 From 号码](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89_From_.E5.8F.B7.E7.A0.81)
  - [8.5路由短信通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.B7.AF.E7.94.B1.E7.9F.AD.E4.BF.A1.E9.80.9A.E7.9F.A5)
- 9Slack 通知
  - [9.1先决条件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E5.85.88.E5.86.B3.E6.9D.A1.E4.BB.B6_4)
  - [9.2格式化 Slack 通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96_Slack_.E9.80.9A.E7.9F.A5)
  - [9.3自定义发件人和收件人](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E5.8F.91.E4.BB.B6.E4.BA.BA.E5.92.8C.E6.94.B6.E4.BB.B6.E4.BA.BA)
  - [9.4Slack 附加项 (Attachments)](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#Slack_.E9.99.84.E5.8A.A0.E9.A1.B9_.28Attachments.29)
  - [9.5Markdown 附件内容](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#Markdown_.E9.99.84.E4.BB.B6.E5.86.85.E5.AE.B9)
  - [9.6路由 Slack 通知](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.B7.AF.E7.94.B1_Slack_.E9.80.9A.E7.9F.A5)
- [10通知事件](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E9.80.9A.E7.9F.A5.E4.BA.8B.E4.BB.B6)
- [11自定义频道](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E8.87.AA.E5.AE.9A.E4.B9.89.E9.A2.91.E9.81.93)
- [12方法列表](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.96.B9.E6.B3.95.E5.88.97.E8.A1.A8)
- [13方法详细说明](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Notification使用说明#.E6.96.B9.E6.B3.95.E8.AF.A6.E7.BB.86.E8.AF.B4.E6.98.8E)

#### 简介

RC_Notification支持通过多种频道发送通知，包括邮件、短信（通过 Nexmo）以及 Slack 。通知还能存到数据库，这样就能在网页界面上显示了。

通常情况下，通知应该是简短、有信息量的消息来通知用户你的应用发生了什么。举例来说，如果你在编写一个在线交易应用，你应该会通过邮件和短信频道来给用户发送一条 「账单已付」 的通知。

#### 创建通知

Royalcms 中一条通知就是一个类（通常存在 app/Notifications 文件夹里）。看不到的话不要担心，运行一下 make:notification 命令就能创建了：

```
php royalcms make:notification InvoicePaid
```

这个命令会在 app/Notifications 目录下生成一个新的通知类。这个类包含 via 方法和几个消息构建方法（比如 toMail 或 toDatabase），它们会针对指定的渠道把通知转换过为对应的消息。

#### 发送通知

使用 Notifiable Trait 通知可以通过两种方法发送： Notifiable trait 的 notify 方法或 Notificationfacade。首先，让我们探索使用 trait ：

```
<?php

namespace App;

use Royalcms\Component\Notifications\Notifiable;
use Royalcms\Component\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use Notifiable;
}
```

默认的 App\User 模型中使用了这个 trait，它包含着一个可以用来发通知的方法：notify 。 notify 方法需要一个通知实例做参数：

```
use App\Notifications\InvoicePaid;

$user->notify(new InvoicePaid($invoice));
```

记住，你可以在任意模型中使用 Royalcms\Component\Notifications\Notifiable trait，而不仅仅是在 User 模型中。

##### 使用 Notification Facade

另外，你可以通过 Notificationfacade来发送通知。它主要用在当你给多个可接收通知的实体发送通知的时候，比如给用户集合发通知。要用 facade 发送通知的话，要把可接收通知的实体和通知的实例传递给 send 方法：

```
RC_Notification::send($users, new InvoicePaid($invoice));
```

##### 指定发送频道

每个通知类都有个 via 方法，它决定了通知在哪个频道上发送。开箱即用的通知频道有 mail, database, broadcast, nexmo, 和 slack 。

via 方法受到一个 $notifiable 实例，它是接收通知的类实例。你可以用 $notifiable 来决定通知用哪个频道来发送：

```
/**
 * 获取通知发送频道
 *
 * @param  mixed  $notifiable
 * @return array
 */
public function via($notifiable)
{
    return $notifiable->prefers_sms ? ['nexmo'] : ['mail', 'database'];
}
```

##### 队列化通知

在队列化通知前你需要配置队列，并 运行队列处理器。

发送通知可能会花很长时间，尤其是发送频道需要调用外部 API 的时候。要加速应用响应的话，可以通过添加 ShouldQueue 接口和 Queueable trait 把通知加入队列。它们两个在使用 make:notification 命令来生成通知文件的时候就已经被导入了，所以你只需要添加到你的通知类就行了：

```
<?php

namespace App\Notifications;

use Royalcms\Component\Bus\Queueable;
use Royalcms\Component\Notifications\Notification;
use Royalcms\Component\Contracts\Queue\ShouldQueue;

class InvoicePaid extends Notification implements ShouldQueue
{
    use Queueable;

    // ...
}
```

一旦加入 ShouldQueue 接口，你就能像平常那样发送通知了。RC_Notification 会检测 ShouldQueue 接口并自动将通知的发送放入队列中。

```
$user->notify(new InvoicePaid($invoice));
```

如果你想延迟发送，你可以通过 delay 方法来链式操作你的通知实例：

```
$when = Carbon::now()->addMinutes(10);

$user->notify((new InvoicePaid($invoice))->delay($when));
```

##### 按需通知

有时候你可能需要将通知发送给某个不是以”用户”身份存储在你的应用中的人。使用RC_Notification::route 方法，你可以在发送通知之前指定 ad-hoc 通知路由信息：

```
RC_Notification::route('mail', 'taylor@Royalcms.com')
            ->route('nexmo', '5555555555')
            ->notify(new InvoicePaid($invoice));
```

#### 邮件通知

##### 格式化邮件消息

如果一条通知支持以邮件发送，你应该在通知类里定义一个 toMail 方法。这个方法将收到一个 $notifiable 实体并返回一个 Royalcms\Component\Notifications\Messages\MailMessage 实例。邮件消息可以包含多行文本也可以是引导链接。我们来看一个 toMail 方法的例子：

```
/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return \Royalcms\Component\Notifications\Messages\MailMessage
 */
public function toMail($notifiable)
{
    $url = url('/invoice/'.$this->invoice->id);

    return (new MailMessage)
                ->line('One of your invoices has been paid!')
                ->action('View Invoice', $url)
                ->line('Thank you for using our application!');
}
```

注意我们在方法中用了 $this->invoice->id ，其实你可以传递应用所需要的任何数据来传递给通知的构造器。

在这个例子中，我们注册了一行文本，引导链接 ，然后又是一行文本。 MailMessage 提供的这些方法简化了对小的事务性的邮件进行格式化操作。邮件频道将会把这些消息组件转换成漂亮的响应式的 HTML 邮件模板并附上文本。

发送邮件通知前，请在 config/app.php 中设置 name 值。 这将会在邮件通知消息的头部和尾部中被使用。

##### 其他通知格式选项

你可以使用 view 方法来指定一个应用于渲染通知电子邮件的自定义模板，而不是在通知类中定义文本的「模板」：

```
/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return \Royalcms\Component\Notifications\Messages\MailMessage
 */
public function toMail($notifiable)
{
    return (new MailMessage)->view(
        'emails.name', ['invoice' => $this->invoice]
    );
}
```

另外，你可以从 toMail 方法中返回一个 mailable 对象 ：

```
use App\Mail\InvoicePaid as Mailable;

/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return Mailable
 */
public function toMail($notifiable)
{
    return (new Mailable($this->invoice))->to($this->user->email);
}
```

##### 错误消息

有些通知是给用户提示错误，比如账单支付失败的提示。你可以通过调用 error 方法来指定这条邮件消息被当做一个错误提示。当邮件消息使用了 error 方法后，引导链接按钮会变成红色而非蓝色：

```
/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return \Royalcms\Component\Notifications\Messages\MailMessage
 */
public function toMail($notifiable)
{
   return (new MailMessage)
                ->error()
                ->subject('Notification Subject')
                ->line('...');
}
```

##### 自定义接收者

当通过 mail 频道来发送通知的时候，通知系统将会自动寻找你的 notifiable 实体中的 email 属性。你可以通过在实体中定义 routeNotificationForMail 方法来自定义邮件地址。

```
<?php

namespace App;

use Royalcms\Component\Notifications\Notifiable;
use Royalcms\Component\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use Notifiable;

    /**
     * 邮件频道的路由
     *
     * @return string
     */
    public function routeNotificationForMail()
    {
        return $this->email_address;
    }
}
```

##### 自定义主题

默认情况下，邮件主题是格式化成了标题格式的通知类的类名。所以如果你对通知类名为 InvoicePaid ，邮件主题将会是 Invoice Paid 。如果你想显式指定消息的主题，你可以在构建消息时调用 subject 方法：

```
/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return \Royalcms\Component\Notifications\Messages\MailMessage
 */
public function toMail($notifiable)
{
    return (new MailMessage)
                ->subject('Notification Subject')
                ->line('...');
}
```

##### 自定义模板

你可以通过发布通知包的资源来修改 HTML 模板和纯文本模板。运行这个命令后，邮件通知模板就被放在了 resources/views/vendor/notifications 文件夹下：

php royalcms vendor:publish --tag=Royalcms-notifications

#### Markdown 邮件通知

Markdown 邮件通知可让您利用邮件通知的预先构建的模板，同时给予您更多自由地撰写更长的自定义邮件。 由于消息是用 Markdown 编写的， RC_Notification 能够为消息呈现漂亮，响应的 HTML 模板，同时还自动生成纯文本对应。



##### 生成消息

要使用相应的 Markdown 模板生成通知，您可以使用 make：notification royalcms命令的 --markdown 选项：

php royalcms make:notification InvoicePaid --markdown=mail.invoice.paid 与所有其他邮件通知一样，使用 Markdown 模板的通知应在其通知类上定义一个 toMail 方法。 但是，不使用 line 和 action 方法来构造通知，而是使用 markdown 方法来指定应该使用的 Markdown 模板的名称：

```
/**
 * 获取通知的邮件展示方式
 *
 * @param  mixed  $notifiable
 * @return \Royalcms\Component\Notifications\Messages\MailMessage
 */
public function toMail($notifiable)
{
    $url = url('/invoice/'.$this->invoice->id);

    return (new MailMessage)
                ->subject('Invoice Paid')
                ->markdown('mail.invoice.paid', ['url' => $url]);
}
```

##### 写消息

Markdown 邮件通知使用 Blade 组件和Markdown语法的组合，允许您轻松构建通知，同时利用Royalcms的预制通知组件：

```
@component('mail::message')
# Invoice Paid

Your invoice has been paid!

@component('mail::button', ['url' => $url])
View Invoice
@endcomponent

Thanks,<br>

@endcomponent
```

##### 按钮组件

按钮组件渲染了一个居中的链接按钮。组件有两个参数， url 和一个可选的参数 color 。支持的颜色有 blue ， green ， 和 red 。你可以根据你的需要向通知中添加任意数量的按钮组件：

```
@component('mail::button', ['url' => $url, 'color' => 'green'])
View Invoice
@endcomponent
```

##### 面板组件

面板部件在面板中呈现给定文本块，该面板具有与通知的其余部分稍微不同的背景颜色。 这将会允许你将给定的文本块引起注意：

```
@component('mail::panel')
This is the panel content.
@endcomponent
```

##### 表格组件

表格组件允许你将一个 Markdown 表格转化成一个 HTML 表格。表格组件接受 Markdown 表格作为内容。支持使用默认的 Markdown 表格对齐语法使表列对齐：

```
@component('mail::table')
| Royalcms       | Table         | Example  |
| ------------- |:-------------:| --------:|
| Col 2 is      | Centered      | $10      |
| Col 3 is      | Right-Aligned | $20      |
@endcomponent
```

##### 自定义组件

您可以将所有 Markdown 通知组件导出到您自己的应用程序中进行自定义。 要导出组件，请使用 vendor：publish royalcms命令来发布 Royalcms-mail 标签：

php royalcms vendor:publish --tag=Royalcms-mail 此命令将 Markdown 邮件组件发布到 resources/views/vendor/mail 目录。 mail 目录将包含一个 html 和一个 markdown 目录，每个目录包含它们各自可用组件的展示方式。 您可以随意自定义这些组件。

##### 自定义CSS

导出组件后， resources/views/vendor/mail/html/themes 目录将包含一个 default.css 文件。 您可以在此文件中自定义 CSS ，并且您的样式将自动内嵌在 Markdown 通知的HTML展示中。

如果您想为 Markdown 组件构建一个全新的主题，只需在 html/themes 目录中写一个新的 CSS 文件，并更改 mail 配置文件中的 theme 选项。



#### 数据库通知

##### 先决条件

database 通知频道在一张数据表里存储通知信息。这张表包含了比如通知类型、JSON 格式数据等描述通知的信息。

你可以查询这张表的内容在应用界面上展示通知。但是在这之前，你需要先创建一个数据表来保存通知。你可以用 notifications:table 命令来生成迁移表：

```
php royalcms notifications:table

php royalcms migrate
```

##### 格式化数据库通知

如果通知支持被存储到数据表中，你应该在通知类中定义一个 toDatabase 或 toArray 方法。这个方法接收 $notifiable 实体参数并返回一个普通的 PHP 数组。这个返回的数组将被转成 JSON 格式并存储到通知数据表的 data 列。我们来看一个 toArray 的例子：

```
/**
 * 获取通知的数组展示方式
 *
 * @param  mixed  $notifiable
 * @return array
 */
public function toArray($notifiable)
{
    return [
        'invoice_id' => $this->invoice->id,
        'amount' => $this->invoice->amount,
    ];
}
```

toDatabase Vs toArray toArray 方法在 broadcast 频道也用到了，它用来决定广播给 JavaScript 客户端的数据。如果你想在 database 和 broadcast 频道中采用两种不同的数组展示方式，你应该定义 toDatabase 方法而非 toArray 方法。



##### 访问通知

一旦通知被存到数据库中，你需要一种方便的方式来从通知实体中访问它们。 Royalcms\Component\Notifications\Notifiable trait 包含一个可以返回这个实体所有通知的 notifications Eloquent 关联。要获取这些通知，你可以像用其他 Eloquent 关联一样来使用这个方法。默认情况下，通知将会以 created_at 时间戳来排序：

```
$user = App\User::find(1);

foreach ($user->notifications as $notification) {
    echo $notification->type;
}
```

如果你只想检索未读通知，你可以使用 unreadNotifications 关联。检索出来的通知也是以 created_at 时间戳来排序的：

```
$user = App\User::find(1);

foreach ($user->unreadNotifications as $notification) {
    echo $notification->type;
}
```

要从 JavaScript 客户端来访问通知的话，你应该定义一个通知控制器来给可通知的实体返回通知，比如给当前用户返回通知。然后你就可以在 JavaScript 客户端来发起对应 URI 的 HTTP 请求了。



##### 标为已读

通常情况下，当用户查看了通知时，你就希望把通知标为已读。Royalcms\Component\Notifications\Notifiable trait 提供了一个 markAsRead 方法，它能在对应的数据库记录里更新 read_at 列：

```
$user = App\User::find(1);

foreach ($user->unreadNotifications as $notification) {
    $notification->markAsRead();
}
```

你可以使用 markAsRead 方法直接操作一个通知集合，而不是一条条遍历每个通知：

```
$user->unreadNotifications->markAsRead();
```

你可以用批量更新的方式来把所有通知标为已读，而不用在数据库里检索：

```
$user = App\User::find(1);

$user->unreadNotifications()->update(['read_at' => Carbon::now()]);
```

当然，你可以通过 delete 通知来把它们从数据库删除：

```
$user->notifications()->delete();
```

#### 广播通知

##### 先决条件

在广播通知前，你应该配置并熟悉 Royalcms 事件广播 服务。事件广播提供了一种 JavaScript 客户端响应服务端 Royalcms 事件的机制。



##### 格式化广播通知

broadcast 频道使用 Royalcms 事件广播 服务来广播通知，它使得 JavaScript 客户端可以实时捕捉通知。如果一条通知支持广播，你应该在通知类里定义一个 toBroadcast 或 toArray 方法。这个方法将收到一个 $notifiable 实体并返回一个普通的 PHP 数组。返回的数组会被编码成 JSON 格式并广播给你的 JavaScript 客户端。我们来看个 toArray 方法的例子：

```
use Royalcms\Component\Notifications\Messages\BroadcastMessage;

/**
 * 获取通知的数组展示方式
 *
 * @param  mixed  $notifiable
 * @return BroadcastMessage
 */
public function toBroadcast($notifiable)
{
    return new BroadcastMessage([
        'invoice_id' => $this->invoice->id,
        'amount' => $this->invoice->amount,
    ]);
}
```

##### 广播队列配置

所有广播通知都排队等待广播。 如果要配置用于广播队列操作的队列连接或队列名称，你可以使用 BroadcastMessage 的 onConnection 和 onQueue 方法：

```
return new BroadcastMessage($data)
                ->onConnection('sqs')
                ->onQueue('broadcasts');
```

除了你指定的数据外，广播通知也包含一个 type 字段，这个字段包含了通知类的类名。



##### 监听通知

通知将会在一个私有频道里进行广播，频道格式为 {notifiable}.{id}。所以，如果你给 ID 为 1 的 App\User 实例发送通知，这个通知就在 App.User.1 私有频道里被发送。当你使用 Royalcms Echo 的时候，你可以很简单地使用 notification 辅助函数来监听一个频道的通知：

```
Echo.private('App.User.' + userId)
    .notification((notification) => {
        console.log(notification.type);
    });
```

##### 自定义通知通道

如果您想自定义应通知实体接收其广播通知的渠道，您可以定义一个 receiveBroadcastNotificationsOn 方法：

```
<?php

namespace App;

use Royalcms\Component\Notifications\Notifiable;
use Royalcms\Component\Broadcasting\PrivateChannel;
use Royalcms\Component\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use Notifiable;

    /**
     * 用户接收的通知广播
     *
     * @return array
     */
    public function receivesBroadcastNotificationsOn()
    {
        return [
            new PrivateChannel('users.'.$this->id),
        ];
    }
}
```

#### 短信通知

#### 先决条件

在 Royalcms 中发送短信通知是基于 Nexmo 服务的。在通过 Nexmo 发送短信通知前，你需要安装 nexmo/client Composer 包并在 config/services.php 配置文件中添加几个配置选项。你可以复制下面的配置示例来开始使用：

```
'nexmo' => [
    'key' => env('NEXMO_KEY'),
    'secret' => env('NEXMO_SECRET'),
    'sms_from' => '15556666666',
],
```

sms_from 选项是短信消息发送者的手机号码。你可以在 Nexmo 控制面板中生成一个手机号码。



##### 格式化短信通知

如果通知支持以短信方式发送，你应该在通知类里定义一个 toNexmo 方法。这个方法将会收到一个 $notifiable 实体并返回一个 Royalcms\Component\Notifications\Messages\NexmoMessage 实例：

```
/**
 * 获取通知的 Nexmo / 短信展示方式
 *
 * @param  mixed  $notifiable
 * @return NexmoMessage
 */
public function toNexmo($notifiable)
{
    return (new NexmoMessage)
                ->content('Your SMS message content');
}
```

##### Unicode 内容

如果您的 SMS 消息包含 unicode 字符，您应该在构建 NexmoMessage 实例时调用 unicode 方法：

```
/**
 * 获取通知的 Nexmo / 短信展示方式
 *
 * @param  mixed  $notifiable
 * @return NexmoMessage
 */
public function toNexmo($notifiable)
{
    return (new NexmoMessage)
                ->content('Your unicode message')
                ->unicode();
}
```

##### 自定义 From 号码

如果你想通过一个手机号来发送某些通知，而这个手机号不同于你的 config/services.php 配置文件中指定的话，你可以在 NexmoMessage 实例中使用 from：

```
/**
 * 获取通知的 Nexmo / 短信展示方式
 *
 * @param  mixed  $notifiable
 * @return NexmoMessage
 */
public function toNexmo($notifiable)
{
    return (new NexmoMessage)
                ->content('Your SMS message content')
                ->from('15554443333');
}
```

##### 路由短信通知

当通过 nexmo 频道来发送通知的时候，通知系统会自动寻找通知实体的 phone_number 属性。如果你想自定义通知被发送的手机号码，你要在通知实体里定义一个 routeNotificationForNexmo 方法。

```
<?php

namespace App;

use Royalcms\Component\Notifications\Notifiable;
use Royalcms\Component\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use Notifiable;

    /**
     * Nexmo 频道的路由通知
     *
     * @return string
     */
    public function routeNotificationForNexmo()
    {
        return $this->phone;
    }
}
```

#### Slack 通知

##### 先决条件

通过 Slack 发送通知前，你必须通过 Composer 安装 Guzzle HTTP 库：

```
composer require guzzlehttp/guzzle
```

你还需要给 Slack 组配置 「Incoming Webhook」 。它将提供你使用 路由 Slack 通知 时用到的 URL。



##### 格式化 Slack 通知

如果通知支持被当做 Slack 消息发送，你应该在通知类里定义一个 toSlack 方法。这个方法将收到一个 $notifiable 实体并且返回一个 Royalcms\Component\Notifications\Messages\SlackMessage 实例。Slack 消息可以包含文本内容以及一个 「attachment」 用来格式化额外文本或者字段数组。我们来看个基本的 toSlack 例子：

```
/**
 * 获取通知的 Slack 展示方式
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    return (new SlackMessage)
                ->content('One of your invoices has been paid!');
}
```

这个例子中，我们只发送了一行文本给 Slack。

##### 自定义发件人和收件人

您可以使用 from 和 to 方法来自定义发件人和收件人。 from 方法接受用户名和表情符号标识符，而 to 方法接受一个频道或用户名：

```
/**
 * 获取通知的 Slack 展示方式
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    return (new SlackMessage)
                ->from('Ghost', ':ghost:')
                ->to('#other')
                ->content('This will be sent to #other');
}
```

你也可以不使用表情符号，改为使用图片作为你的 logo：

```
/**
 * 获取通知的 Slack 展示方式
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    return (new SlackMessage)
                ->from('Royalcms')
                ->image('https://Royalcms.com/favicon.png')
                ->content('This will display the Royalcms logo next to the message');
}
```

##### Slack 附加项 (Attachments)

你可以给 Slack 消息添加 “附加项”。附加项提供了比简单文本消息更丰富的格式化选项。在这个例子中，我们将发送一条有关应用中异常的错误通知，它里面有个可以查看这个异常更多详情的链接：

```
/**
 * 获取通知的 Slack 展示方式。
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    $url = url('/exceptions/'.$this->exception->id);

    return (new SlackMessage)
                ->error()
                ->content('Whoops! Something went wrong.')
                ->attachment(function ($attachment) use ($url) {
                    $attachment->title('Exception: File Not Found', $url)
                               ->content('File [background.jpg] was not found.');
                });
}
```

附加项也允许你指定一个应该被展示给用户的数据的数组。给定的数据将会以表格样式展示出来，这能方便阅读：

```
/**
 * 获取通知的 Slack 展示方式
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    $url = url('/invoices/'.$this->invoice->id);

    return (new SlackMessage)
                ->success()
                ->content('One of your invoices has been paid!')
                ->attachment(function ($attachment) use ($url) {
                    $attachment->title('Invoice 1322', $url)
                               ->fields([
                                    'Title' => 'Server Expenses',
                                    'Amount' => '$1,234',
                                    'Via' => 'American Express',
                                    'Was Overdue' => ':-1:',
                                ]);
                });
}
```

##### Markdown 附件内容

如果一些附件字段包含 Markdown ，您可以使用 markdown 方法指示 Slack 解析并将给定的附件字段显示为 Markdown 格式的文本：

```
/**
 * 获取通知的 Slack 展示方式
 *
 * @param  mixed  $notifiable
 * @return SlackMessage
 */
public function toSlack($notifiable)
{
    $url = url('/exceptions/'.$this->exception->id);

    return (new SlackMessage)
                ->error()
                ->content('Whoops! Something went wrong.')
                ->attachment(function ($attachment) use ($url) {
                    $attachment->title('Exception: File Not Found', $url)
                               ->content('File [background.jpg] was **not found**.')
                               ->markdown(['title', 'text']);
                });
}
```

##### 路由 Slack 通知

要把 Slack 通知路由到正确的位置，你要在通知实体中定义 routeNotificationForSlack 方法。它返回通知要被发往的 URL 回调地址。URL 可以通过在 Slack 组里面添加 “Incoming Webhook” 服务来生成。

```
<?php

namespace App;

use Royalcms\Component\Notifications\Notifiable;
use Royalcms\Component\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use Notifiable;

    /**
     * Slack 频道的通知路由
     *
     * @return string
     */
    public function routeNotificationForSlack()
    {
        return $this->slack_webhook_url;
    }
}
```

#### 通知事件

当通知发送后，通知系统就会触发 Royalcms\Component\Notifications\Events\NotificationSent 事件。它包含了 「notifiable」 实体和通知实例本身。你应该在 EventServiceProvider 中注册监听器：

```
/**
 * 应用中的事件监听映射
 *
 * @var array
 */
protected $listen = [
    'Royalcms\Component\Notifications\Events\NotificationSent' => [
        'App\Listeners\LogNotification',
    ],
];
```

注册完监听器后，使用 event:generate royalcms 命令来快速生成监听器类。

在事件监听器中，你可以访问事件中的 notifiable, notification, 和 channel 属性，来了解通知接收者和通知本身：

```
/**
 * 处理事件
 *
 * @param  NotificationSent  $event
 * @return void
 */
public function handle(NotificationSent $event)
{
    // $event->channel
    // $event->notifiable
    // $event->notification
}
```

#### 自定义频道

Royalcms 提供了开箱即用的通知频道，但是你可能会想编写自己的驱动来通过其他频道发送通知。Royalcms 很容易实现。首先，定义一个包含 send 方法的类。这个方法应该收到两个参数：$notifiable 和 $notification:

```
<?php

namespace App\Channels;

use Royalcms\Component\Notifications\Notification;

class VoiceChannel
{
    /**
     * 发送给定通知
     *
     * @param  mixed  $notifiable
     * @param  \Royalcms\Component\Notifications\Notification  $notification
     * @return void
     */
    public function send($notifiable, Notification $notification)
    {
        $message = $notification->toVoice($notifiable);

        // 将通知发送给 $notifiable 实例
    }
}
```

一旦定义了通知频道类，你应该在所有通知里通过 via 方法来简单地返回这个频道的类名。

```
<?php

namespace App\Notifications;

use Royalcms\Component\Bus\Queueable;
use App\Channels\VoiceChannel;
use App\Channels\Messages\VoiceMessage;
use Royalcms\Component\Notifications\Notification;
use Royalcms\Component\Contracts\Queue\ShouldQueue;

class InvoicePaid extends Notification
{
    use Queueable;

    /**
     * 获取通知频道
     *
     * @param  mixed  $notifiable
     * @return array|string
     */
    public function via($notifiable)
    {
        return [VoiceChannel::class];
    }

    /**
     * 获取通知的声音展示方式
     *
     * @param  mixed  $notifiable
     * @return VoiceMessage
     */
    public function toVoice($notifiable)
    {
        // ...
    }
}
```

#### 方法列表

| 编号 |         方法名称         |                    简单描述                     |
| :--: | :----------------------: | :---------------------------------------------: |
|  1   |          send()          |        将给定通知发送给给定的可通知实体         |
|  2   |        sendNow()         |               立即发送给定的通知                |
|  3   | shouldSendNotification() |              确定是否可以发送通知               |
|  4   |   queueNotification()    |            对给定的通知实例进行排队             |
|  5   |   formatNotifiables()    | 如有必要，将notifiables格式化为Collection/array |
|  6   |        channel()         |                  获取频道实例                   |
|  7   |    getDefaultDriver()    |           获取默认的通道驱动程序名称            |
|  8   |      deliversVia()       |           获取默认的通道驱动程序名称            |
|  9   |       deliverVia()       |            设置默认通道驱动程序名称             |

#### 方法详细说明

1、send()

- 将给定通知发送给给定的可通知实体：

```
$styles = RC_Notification::send($notifiables, $notification);
```

| 1    | $notifiables  | mixed | 通知模型 |
| ---- | ------------- | ----- | -------- |
| 2    | $notification | mixed | 通知实例 |

2、sendNow()

- 立即发送给定的通知：

```
$result = RC_Notification::sendNow($notifiables, $notification, array $channels = null);
```

| 1    | $notifiables  | mixed  | 通知模型 |
| ---- | ------------- | ------ | -------- |
| 2    | $notification | mixed  | 通知实例 |
| 3    | $channels     | string | 频道     |

3、shouldSendNotification()

- 确定是否可以发送通知：

```
$result = RC_Notification::shouldSendNotification($notifiable, $notification, $channel);
```

| 1    | $notifiables  | mixed  | 通知模型 |
| ---- | ------------- | ------ | -------- |
| 2    | $notification | mixed  | 通知实例 |
| 3    | $channels     | string | 频道     |

4、queueNotification()

- 对给定的通知实例进行排队：

```
$result = RC_Notification::queueNotification($notifiables, $notification);
```

| 1    | $notifiables  | mixed | 通知模型 |
| ---- | ------------- | ----- | -------- |
| 2    | $notification | mixed | 通知实例 |

5、formatNotifiables()

- 如有必要，将notifiables格式化为Collection/array

```
$result = RC_Notification::formatNotifiables($notifiables);
```

| 1    | $notifiables | mixed | 通知模型 |
| ---- | ------------ | ----- | -------- |
|      |              |       |          |

6、channel()

- 获取频道实例：

```
$result = RC_Notification::channel($name = null);
```

| 1    | $name | null | 频道名称 |
| ---- | ----- | ---- | -------- |
|      |       |      |          |

7、getDefaultDriver()

- 获取默认的通道驱动程序名称

```
$result = RC_Notification::getDefaultDriver();
```

8、deliversVia()

- 获取默认的通道驱动程序名称：

```
$result = RC_Notification::deliversVia();
```

9、deliverVia()

- 设置默认通道驱动程序名称：

```
$result = RC_Notification::deliverVia();
```