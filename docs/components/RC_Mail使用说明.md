### ecjia后台RC_Mail使用说明



#### 方法列表

| 编号 |   方法名    | 简单描述 |
| :--: | :---------: | :------: |
|  1   | send_mail() | 邮件发送 |

#### 方法详细说明

1、send_mail()

- 邮件发送，调用示例：

```
public function send_mail($name, $email, $subject, $content, $type = 0, $notification = false)
```

| 1    | $name         | string | 接收人姓名                    |
| ---- | ------------- | ------ | ----------------------------- |
| 2    | $email        | string | 接收人邮件地址                |
| 3    | $subject      | string | 邮件标题                      |
| 4    | $content      | string | 邮件内容                      |
| 5    | $type         | int    | 0 普通邮件，1 HTML邮件        |
| 6    | $notification | bool   | true 要求回执，false 不用回执 |