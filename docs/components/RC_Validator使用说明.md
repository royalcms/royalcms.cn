### ecjia后台RC_Validator使用说明



#### 目录

 [隐藏] 

- [1方法说明](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.96.B9.E6.B3.95.E8.AF.B4.E6.98.8E)
- [2方法位置](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.96.B9.E6.B3.95.E4.BD.8D.E7.BD.AE)
- 3验证规则清单与功能
  - [3.1accepted#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#accepted.23)
  - [3.2active_url#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#active_url.23)
  - [3.3after:date#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#after:date.23)
  - [3.4alpha#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#alpha.23)
  - [3.5alpha_dash#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#alpha_dash.23)
  - [3.6alpha_num#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#alpha_num.23)
  - [3.7array#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#array.23)
  - [3.8before:date#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#before:date.23)
  - [3.9between:min,max#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#between:min.2Cmax.23)
  - [3.10boolean#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#boolean.23)
  - [3.11confirmed#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#confirmed.23)
  - [3.12date#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#date.23)
  - [3.13date_format:format#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#date_format:format.23)
  - [3.14different:field#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#different:field.23)
  - [3.15digits:value#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#digits:value.23)
  - [3.16digits_between:min,max#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#digits_between:min.2Cmax.23)
  - [3.17email#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#email.23)
  - [3.18exists:table,column#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#exists:table.2Ccolumn.23)
  - [3.19image#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#image.23)
  - [3.20in:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#in:foo.2Cbar.2C....23)
  - [3.21integer#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#integer.23)
  - [3.22ip#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#ip.23)
  - [3.23json#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#json.23)
  - [3.24max:value#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#max:value.23)
  - [3.25mimes:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#mimes:foo.2Cbar.2C....23)
  - [3.26min:value#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#min:value.23)
  - [3.27not_in:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#not_in:foo.2Cbar.2C....23)
  - [3.28numeric#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#numeric.23)
  - [3.29regex:pattern#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#regex:pattern.23)
  - [3.30required#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required.23)
  - [3.31required_if:anotherfield,value,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_if:anotherfield.2Cvalue.2C....23)
  - [3.32required_unless:anotherfield,value,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_unless:anotherfield.2Cvalue.2C....23)
  - [3.33required_with:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_with:foo.2Cbar.2C....23)
  - [3.34required_with_all:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_with_all:foo.2Cbar.2C....23)
  - [3.35required_without:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_without:foo.2Cbar.2C....23)
  - [3.36required_without_all:foo,bar,...#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#required_without_all:foo.2Cbar.2C....23)
  - [3.37same:field#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#same:field.23)
  - [3.38size:value#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#size:value.23)
  - [3.39string#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#string.23)
  - [3.40timezone#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#timezone.23)
  - [3.41url#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#url.23)
- 4处理错误消息
  - [4.1查看特定字段的第一个错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.9F.A5.E7.9C.8B.E7.89.B9.E5.AE.9A.E5.AD.97.E6.AE.B5.E7.9A.84.E7.AC.AC.E4.B8.80.E4.B8.AA.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
  - [4.2查看特定字段的所有错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.9F.A5.E7.9C.8B.E7.89.B9.E5.AE.9A.E5.AD.97.E6.AE.B5.E7.9A.84.E6.89.80.E6.9C.89.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
  - [4.3查看所有字段的所有错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.9F.A5.E7.9C.8B.E6.89.80.E6.9C.89.E5.AD.97.E6.AE.B5.E7.9A.84.E6.89.80.E6.9C.89.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
  - [4.4判断特定字段是否含有错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E5.88.A4.E6.96.AD.E7.89.B9.E5.AE.9A.E5.AD.97.E6.AE.B5.E6.98.AF.E5.90.A6.E5.90.AB.E6.9C.89.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
  - [4.5获取格式化后的错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E8.8E.B7.E5.8F.96.E6.A0.BC.E5.BC.8F.E5.8C.96.E5.90.8E.E7.9A.84.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
  - [4.6获取所有格式化后的错误消息#](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E8.8E.B7.E5.8F.96.E6.89.80.E6.9C.89.E6.A0.BC.E5.BC.8F.E5.8C.96.E5.90.8E.E7.9A.84.E9.94.99.E8.AF.AF.E6.B6.88.E6.81.AF.23)
- [5使用方法](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E4.BD.BF.E7.94.A8.E6.96.B9.E6.B3.95)
- [6注意事项](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Validator使用说明#.E6.B3.A8.E6.84.8F.E4.BA.8B.E9.A1.B9)

#### 方法说明

数据单条或者多条的多规则验证。

#### 方法位置

vendor/royalcms/framework/Royalcms/Component/Validation

#### 验证规则清单与功能

```
Accepted
Active URL
After (Date)
Alpha
Alpha Dash
Alpha Numeric
Array
Before (Date)
Between
Boolean
Confirmed
Date
Date Format
Different
Digits
Digits Between
E-Mail
Exists (Database)
Image (File)
In
Integer
IP Address
JSON
Max
MIME Types (File)
Min
Not In
Numeric
Regular Expression
Required
Required If
Required Unless
Required With
Required With All
Required Without
Required Without All
Same
Size
String
Timezone
Unique (Database)
URL
```

##### accepted#

验证字段值是否为 yes、on、1、或 true。这在确认「服务条款」是否同意时相当有用。



##### active_url#

验证字段值是否为一个有效的网址，会通过 PHP 的 checkdnsrr 函数来验证。



##### after:date#

验证字段是否是在指定日期之后。这个日期将会通过 strtotime 函数来验证。

'start_date' => 'required|date|after:tomorrow' 作为替换 strtotime 传递的日期字符串，你可以指定其它的字段来比较日期：

'finish_date' => 'required|date|after:start_date'



##### alpha#

验证字段值是否仅包含字母字符。



##### alpha_dash#

验证字段值是否仅包含字母、数字、破折号（ - ）以及下划线（ _ ）。



##### alpha_num#

验证字段值是否仅包含字母、数字。



##### array#

验证字段必须是一个 PHP array。



##### before:date#

验证字段是否是在指定日期之前。这个日期将会使用 PHP strtotime 函数来验证。



##### between:min,max#

验证字段值的大小是否介于指定的 min 和 max 之间。字符串、数值或是文件大小的计算方式和 size 规则相同。



##### boolean#

验证字段值是否能够转换为布尔值。可接受的参数为 true、false、1、0、"1" 以及 "0"。



##### confirmed#

验证字段值必须和 foo_confirmation 的字段值一致。例如，如果要验证的字段是 password，就必须和输入数据里的 password_confirmation 的值保持一致。



##### date#

验证字段值是否为有效日期，会根据 PHP 的 strtotime 函数来做验证。



##### date_format:format#

验证字段值符合定义的日期格式，通过 PHP 的 date_parse_from_format 函数来验证。



##### different:field#

验证字段值是否和指定_字段（ field ）_不同。



##### digits:value#

验证字段值是否为 numeric 且长度为 value。



##### digits_between:min,max#

验证字段值的长度是否在 min 和 max 之间。



##### email#

验证字段值是否符合 e-mail 格式。



##### exists:table,column#

验证字段值是否存在指定的数据表中。

Exists 规则的基本使用方法#

'state' => 'exists:states' 指定一个特定的字段名称#

'state' => 'exists:states,abbreviation' 也可以指定更多的条件，它们会被加到「where」查询语句中：

'email' => 'exists:staff,email,account_id,1' 你也可以传递 NULL 或 NOT_NULL 至「where」语句：

'email' => 'exists:staff,email,deleted_at,NULL'

'email' => 'exists:staff,email,deleted_at,NOT_NULL'



##### image#

验证字段文件必须为图片格式（ jpeg、png、bmp、gif、 或 svg ）。



##### in:foo,bar,...#

验证字段值是否有在指定的列表里面。



##### integer#

验证字段值是否是整数。



##### ip#

验证字段值是否符合 IP address 的格式。



##### json#

验证字段是否是一个有效的 JSON 字符串。



##### max:value#

字段值必须小于或等于 value 。字符串、数值或是文件大小的计算方式和 size 规则相同。



##### mimes:foo,bar,...#

验证字段文件的 MIME 类型是否符合列表中指定的格式。

MIME 规则基本用法#

'photo' => 'mimes:jpeg,bmp,png' 即使你可能只需要验证指定扩展名，但此规则实际上会验证文件的 MIME 类型，其通过读取文件的内容以猜测它的 MIME 类型。

完整的 MIME 类型及对应的扩展名列表可以在下方链接找到： http://svn.apache.org/repos/asf/httpd/httpd/trunk/docs/conf/mime.types



##### min:value#

字段值必须大于或等于 value。字符串、数值或是文件大小的计算方式和 size 规则相同。



##### not_in:foo,bar,...#

验证字段值是否不在指定的列表里。



##### numeric#

验证字段值是否为数值。



##### regex:pattern#

验证字段值是否符合指定的正则表达式。

注意：当使用 regex 规则时，你必须使用数组，而不是使用管道分隔规则，特别是当正则表达式含有管道符号时。



##### required#

验证字段必须存在输入数据，且不为空。字段符合下方任一条件时即为「空」：

该值为 null。 该值为空字符串。 该值为空数组或空的可数对象。 该值为没有路径的上传文件。



##### required_if:anotherfield,value,...#

如果指定的其它字段（ anotherfield ）等于任何一个 value 时，此字段为必填。



##### required_unless:anotherfield,value,...#

如果指定的其它字段（ anotherfield ）等于任何一个 value 时，则此字段为不必填。



##### required_with:foo,bar,...#

如果指定的字段中的 任意一个 有值，则此字段为必填。



##### required_with_all:foo,bar,...#

如果指定的 所有 字段都有值，则此字段为必填。

##### required_without:foo,bar,...#

如果缺少任意一个指定的字段，则此字段为必填。



##### required_without_all:foo,bar,...#

如果所有指定的字段都没有值，则此字段为必填。



##### same:field#

验证字段值和指定的 字段（ field ） 值是否相同。



##### size:value#

验证字段值的大小是否符合指定的 value 值。对于字符串来说，value 为字符数。对于数字来说，value 为某个整数值。对文件来说，size 对应的是文件大小（单位 kb ）。



##### string#

验证字段值的类型是否为字符串。



##### timezone#

验证字段值是否是有效的时区，会根据 PHP 的 timezone_identifiers_list 函数来判断。

unique:table,column,except,idColumn#

在指定的数据表中，验证字段必须是唯一的。如果没有指定 column，将会使用字段本身的名称。

指定一个特定的字段名称：

'email' => 'unique:users,email_address' 自定义数据库连接

有时候你可能需要自定义一个连接，来通过 Validator 对数据库进行查找。如上面所示，设置 unique:users 作为验证规则，通过默认数据库连接来做数据库查找。如果要重写验证规则，可在指定的连接的表单名称后面加上「.」：

'email' => 'unique:connection.users,email_address' 强迫 Unique 规则忽略指定 ID：

有时候，你希望在验证字段时对指定 ID 进行忽略。例如，在「更新个人资料」页面会包含用户名、邮箱等字段。这时你会想要验证更新的 e-mail 值是否为唯一的。如果用户仅更改了名称字段而不是 e-mail 字段，就不需要抛出验证错误，因为此用户已经是这个 e-mail 的拥有者了。假设用户提供的 e-mail 已经被其他用户使用，则需要抛出验证错误。若要用指定规则来忽略用户 ID，则应该把要发送的 ID 当作第三个参数：

'email' => 'unique:users,email_address,'.$user->id 如果你的数据表使用的主键名称不是 id，那么你可以在第四个参数中来指定它：

'email' => 'unique:users,email_address,'.$user->id.',user_id' 增加额外的 Where 语句：

你也可以指定更多的条件到「where」查询语句：

'email' => 'unique:users,email_address,NULL,id,account_id,1' 上述规则中，只有 account_id 为 1 的数据列会被包含在 unique 规则的验证。



##### url#

根据 PHP 的 filter_var 函数来验证字段是否符合 URL 格式。

#### 处理错误消息

调用一个 Validator 实例的 errors 方法，会得到一个 Illuminate\Support\MessageBag 的实例，里面有许多可让你操作错误消息的便利方法。

##### 查看特定字段的第一个错误消息#

如果要查看特定字段的第一个错误消息，可以使用 first 方法：

```
$messages = $validator->errors();
echo $messages->first('email');
```

##### 查看特定字段的所有错误消息#

如果你想通过指定字段来简单的获取所有消息中的一个数组，则可以使用 get 方法：

```
foreach ($messages->get('email') as $message) {
    //
}
```

##### 查看所有字段的所有错误消息#

如果你想要得到所有字段的消息数组，则可以使用 all 方法：

```
foreach ($messages->all() as $message) {
    //
}
```

##### 判断特定字段是否含有错误消息#

```
if ($messages->has('email')) {
    //
}
```

##### 获取格式化后的错误消息#

```
echo $messages->first('email', '<p>:message</p>');
```

##### 获取所有格式化后的错误消息#

```
foreach ($messages->all('<li>:message</li>') as $message) {
    //
}
```

#### 使用方法

```
$validator = RC_Validator::make($_POST, array(
    'email' => 'required|email',
    'username' => 'required',
));
if ($validator->fails()) {
    $this->showmessage(__('输入的信息不正确！'), ecjia::MSGSTAT_ERROR | ecjia::MSGTYPE_JSON);
}
```

#### 注意事项

时间判断函数误差问题