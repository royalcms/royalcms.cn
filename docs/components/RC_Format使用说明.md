### ECJiaWiki:Ecjia后台RC Format使用说明

#### 方法列表

| 编号 |           方法名称           |                           简单描述                           |
| :--: | :--------------------------: | :----------------------------------------------------------: |
|  1   |            date()            |                          日期格式化                          |
|  2   |            week()            |                         获取当前星期                         |
|  3   |      trailingslashit()       |                       附加一个尾部斜杠                       |
|  4   |     untrailingslashit()      |                如果存在，则删除正斜杠和反斜杠                |
|  5   |       normalize_path()       |                      规范化文件系统路径                      |
|  6   |         path_join()          |                 将两个文件系统路径连接在一起                 |
|  7   |      path_is_absolute()      | 测试给定文件系统路径是否为绝对路径("/foo/bar", "c: windows") |
|  8   |        format_size()         |               根据大小返回标准单位 KB MB GB等                |
|  9   |        format_bytes()        |                   将含有单位的数字转成字节                   |
|  10  |         format_js()          |                将文本格式成适合js输出的字符串                |
|  11  |      format_textarea()       |                       格式化文本域内容                       |
|  12  |       format_script()        |                   转义 javascript 代码标记                   |
|  13  |          esc_url()           |                        检查并清除URL                         |
|  14  |        esc_url_raw()         |                  对数据库使用执行esc_url()                   |
|  15  |       _deep_replace()        |      执行深度字符串替换操作以确保$search中的值不再存在       |
|  16  |       urlencode_deep()       |            浏览数组并对要在URL中使用的值进行编码             |
|  17  |     rawurlencode_deep()      |            浏览数组并对原始编码要在URL中使用的值             |
|  18  |          esc_attr()          |                         转义HTML属性                         |
|  19  |           esc_js()           |         转义单引号，html特殊字符“<>＆，并修复行结尾          |
|  20  |          esc_html()          |                         转义为HTML块                         |
|  21  |        esc_textarea()        |                       为文本区域值转义                       |
|  22  |    _check_invalid_utf8()     |                检查字符串中是否存在无效的utf8                |
|  23  |       _specialchars()        |                将多个特殊字符转换为其HTML实体                |
|  24  |    _specialchars_decode()    |                将多个HTML实体转换为其特殊字符                |
|  25  |  _cleanup_header_comment()   |         从WP使用的文件头中删除关闭注释并关闭php标记          |
|  26  | _texturize_pushpop_element() | 搜索已禁用的元素标记。 推送元素在标签打开时堆叠并在标签关闭时弹出。 假设$text的第一个字符是标记打开。 |
|  27  |       sanitize_title()       |                    清除标题或返回回退标题                    |
|  28  |     sanitize_file_name()     |                 清除文件名，用破折号替换空白                 |
|  29  |       remove_accents()       |                 将所有重音符转换为ASCII字符                  |
|  30  |         seems_utf8()         |                  检查字符串是否是utf8编码的                  |
|  31  |    sanitize_html_class()     |              清理HTML类名以确保它只包含有效字符              |
|  32  |        sanitize_url()        |                           URL过滤                            |
|  33  |        sanitize_key()        |                         清理字符串键                         |
|  34  |       sanitize_email()       |                删除电子邮件中不允许的所有字符                |
|  35  |    is_serialized_string()    |                检查序列化数据是否为字符串类型                |
|  36  |      maybe_serialize()       |                    序列化数据（如果需要）                    |
|  37  |     maybe_unserialize()      |                仅当值被序列化时才将其非序列化                |
|  38  |       is_serialized()        |                   检查值以确定是否已序列化                   |
|  39  |        removeEmoji()         |                      删除emoji表情符号                       |
|  40  |        filterEmoji()         |                      过滤emoji表情符号                       |

#### 方法详细说明

1、date()

- 日期格式化：

```
$styles = RC_Format::date($timestamp, $showtime = 0);
```

| 1    | $timestamp | int  | 时间戳        |
| ---- | ---------- | ---- | ------------- |
| 2    | $showtime  | int  | 时间，默认为0 |

2、week()

- 获取当前星期：

```
$result = RC_Format::week($timestamp);
```

| 1    | $timestamp | int  | 时间戳 |
| ---- | ---------- | ---- | ------ |
|      |            |      |        |

3、trailingslashit()

- 附加一个尾部斜杠：

```
$result = RC_Format::trailingslashit($string);
```

| 1    | $string | string | 要添加尾部斜杠的内容 |
| ---- | ------- | ------ | -------------------- |
|      |         |        |                      |

4、untrailingslashit()

- 如果存在，则删除正斜杠和反斜杠：

```
$result = RC_Format::untrailingslashit($string);
```

| 1    | $string | string | 从何处删除尾部斜杠 |
| ---- | ------- | ------ | ------------------ |
|      |         |        |                    |

5、normalize_path()

- 规范化文件系统路径：

```
$result = RC_Format::normalize_path($path);
```

| 1    | $path | string | 规范化的路径 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

6、path_join()

- 将两个文件系统路径连接在一起：

```
$result = RC_Format::path_join($base, $path);
```

| 1    | $base | string | 基础 |
| ---- | ----- | ------ | ---- |
| 2    | $path | string | 路径 |

7、path_is_absolute()

- 测试给定文件系统路径是否为绝对路径("/foo/bar", "c: windows")：

```
$result = RC_Format::path_is_absolute($path);
```

| 1    | $path | string | 路径 |
| ---- | ----- | ------ | ---- |
|      |       |        |      |

8、format_size()

- 根据大小返回标准单位 KB MB GB等：

```
$result = RC_Format::format_size($size, $decimals = 2);
```

| 1    | $size     | string | 大小   |
| ---- | --------- | ------ | ------ |
| 2    | $decimals | int    | 小数点 |

9、format_bytes()

- 将含有单位的数字转成字节：

```
$result = RC_Format::format_bytes($val);
```

| 1    | $val | string | 带单位的数字 |
| ---- | ---- | ------ | ------------ |
|      |      |        |              |

10、format_js()

- 将文本格式成适合js输出的字符串：

```
$result = RC_Format::format_js($string, $isjs = 1);
```

| 1    | $string | string | 需要处理的字符串                 |
| ---- | ------- | ------ | -------------------------------- |
| 2    | $isjs   | int    | 是否执行字符串格式化，默认为执行 |

11、format_textarea()

- 格式化文本域内容：

```
$result = RC_Format::format_textarea($string);
```

| 1    | $string | string | 文本域内容 |
| ---- | ------- | ------ | ---------- |
|      |         |        |            |

12、format_script()

- 转义 javascript 代码标记：

```
$result = RC_Format::format_script($str);
```

| 1    | $str | string | 需要处理的内容 |
| ---- | ---- | ------ | -------------- |
|      |      |        |                |

13、esc_url()

- 检查并清除URL：

```
$result = RC_Format::esc_url($url, $protocols = null, $_context = 'display');
```

| 1    | $url       | string | 要检查的URL                             |
| ---- | ---------- | ------ | --------------------------------------- |
| 2    | $protocols | array  | 可选的。 可接受的协议                   |
| 3    | $_context  | string | 私有的，使用esc_url_raw()进行数据库使用 |

14、esc_url_raw()

- 对数据库使用执行esc_url：

```
$result = RC_Format::esc_url_raw($url, $protocols = null);
```

| 1    | $url       | string | 要检查的URL  |
| ---- | ---------- | ------ | ------------ |
| 2    | $protocols | array  | 可接受的协议 |

15、_deep_replace()

- 执行深度字符串替换操作以确保$search中的值不再存在：

```
$result = RC_Format::_deep_replace($search, $subject);
```

| 1    | $search  | array  | 正在搜索的值         |
| ---- | -------- | ------ | -------------------- |
| 2    | $subject | string | 被搜索和替换的字符串 |

16、urlencode_deep()

- 浏览数组并对要在URL中使用的值进行编码：

```
$result = RC_Format::urlencode_deep($value);
```

| 1    | $value | array | 要编码的数组或字符串 |
| ---- | ------ | ----- | -------------------- |
|      |        |       |                      |

17、rawurlencode_deep()

- 浏览数组并对原始编码要在URL中使用的值：

```
$result = RC_Format::rawurlencode_deep($value);
```

| 1    | $value | array | 要编码的数组或字符串 |
| ---- | ------ | ----- | -------------------- |
|      |        |       |                      |

18、esc_attr()

- 转义HTML属性：

```
$result = RC_Format::esc_attr($text);
```

| 1    | $text | string | 要转义的文本 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

19、esc_js()

- 转义单引号，html特殊字符“<>＆，并修复行结尾：

```
$result = RC_Format::esc_js($text);
```

| 1    | $text | string | 要转义的文本 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

20、esc_html()

- 转义为HTML块：

```
$result = RC_Format::esc_html($text);
```

| 1    | $text | string | 要转义的文本 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

21、esc_textarea()

- 为文本区域值转义：

```
$result = RC_Format::esc_textarea($text);
```

| 1    | $text | string | 要转义的文本 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

22、_check_invalid_utf8()

- 检查字符串中是否存在无效的utf8：

```
$result = RC_Format::_check_invalid_utf8($string, $strip = false);
```

| 1    | $string | string  | 要检查的文本                                  |
| ---- | ------- | ------- | --------------------------------------------- |
| 2    | $strip  | boolean | 可选的。是否尝试删除无效的utf8。默认值为false |

23、_specialchars()

- 将多个特殊字符转换为其HTML实体：

```
$result = RC_Format::_specialchars($string, $quote_style = ENT_NOQUOTES, $charset = false, $double_encode = false);
```

| 1    | $string        | string  | 要转义的文本                                                 |
| ---- | -------------- | ------- | ------------------------------------------------------------ |
| 2    | $quote_style   | mixed   | 可选的。ENT_NOQUOTES为转换双引号；ENT_QUOTES则转换为双引号；ENT_NOQUOTES为转换为none；single转换为单引号；double转换为double，否则设置为both。默认为ENT_NOQUOTES |
| 3    | $charset       | string  | 可选的。 字符串的字符编码。 默认值为false                    |
| 4    | $double_encode | boolean | 可选的。是否对现有HTML实体进行编码。默认值为false            |

24、_specialchars_decode()

- 将多个HTML实体转换为其特殊字符：

```
$result = RC_Format::_specialchars_decode($string, $quote_style = ENT_NOQUOTES);
```

| 1    | $string      | string | 要转义的文本                                                 |
| ---- | ------------ | ------ | ------------------------------------------------------------ |
| 2    | $quote_style | mixed  | 可选的。ENT_NOQUOTES为转换双引号；ENT_QUOTES则转换为双引号；ENT_NOQUOTES为转换为none；single转换为单引号；double转换为double，否则设置为both。默认为ENT_NOQUOTES |

25、_cleanup_header_comment()

- 从WP使用的文件头中删除关闭注释并关闭php标记：

```
$result = RC_Format::_cleanup_header_comment($str);
```

| 1    | $str | string | 内容 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

26、_texturize_pushpop_element()

- 搜索已禁用的元素标记。推送元素在标签打开时堆叠并在标签关闭时弹出。 假设$text的第一个字符是标记打开：

```
$result = RC_Format::_texturize_pushpop_element($text, &$stack, $disabled_elements, $opening = '<', $closing = '>');
```

| 1    | $text              | string | 要检查的文本。第一个字符假定为$opening |
| ---- | ------------------ | ------ | -------------------------------------- |
| 2    | $stack             | array  | 用作已打开标记元素堆栈的数组           |
| 3    | $disabled_elements | string | 要与格式化为regexp子表达式匹配的标记   |
| 4    | $opening           | string | 标签开头字符，假定为1个字符长          |
| 5    | $closing           | string | 标记结束字符                           |

27、sanitize_title()

- 清除标题或返回回退标题：

```
$result = RC_Format::sanitize_title($title, $fallback_title = '', $context = 'save');
```

| 1    | $title          | string | 要检查的字符串                       |
| ---- | --------------- | ------ | ------------------------------------ |
| 2    | $fallback_title | string | 可选的。如果$title为空，则使用的标题 |
| 3    | $context        | string | 可选的。为其清理字符串的操作         |

28、sanitize_file_name()

- 清除文件名，用破折号替换空白：

```
$result = RC_Format::sanitize_file_name($filename);
```

| 1    | $filename | string | 要检查的文件名 |
| ---- | --------- | ------ | -------------- |
|      |           |        |                |

29、remove_accents()

- 将所有重音符转换为ASCII字符：

```
$result = RC_Format::remove_accents($string);
```

| 1    | $string | string | 可能包含重音字符的文本 |
| ---- | ------- | ------ | ---------------------- |
|      |         |        |                        |

30、seems_utf8()

- 检查字符串是否是utf8编码的：

```
$result = RC_Format::seems_utf8($str);
```

| 1    | $str | string | 要检查的字符串 |
| ---- | ---- | ------ | -------------- |
|      |      |        |                |

31、sanitize_html_class()

- 清理HTML类名以确保它只包含有效字符：

```
$result = RC_Format::sanitize_html_class($class, $fallback = '');
```

| 1    | $class    | string | 要检查的类名                               |
| ---- | --------- | ------ | ------------------------------------------ |
| 2    | $fallback | string | 可选的。如果检查结束为空字符串，则返回该值 |

32、sanitize_url()

- URL过滤：

```
$result = RC_Format::sanitize_url($url , $check = 'http://');
```

| 1    | $url   | string | 参数字符串，一个urld地址,对url地址进行校正 |
| ---- | ------ | ------ | ------------------------------------------ |
| 2    | $check | string | 检查的协议                                 |

33、sanitize_key()

- 清理字符串键：

```
$result = RC_Format::sanitize_key($key);
```

| 1    | $key | string | 字符串 |
| ---- | ---- | ------ | ------ |
|      |      |        |        |

34、sanitize_email()

- 删除电子邮件中不允许的所有字符：

```
$result = RC_Format::sanitize_email($email);
```

| 1    | $email | string | 要过滤的电子邮件地址 |
| ---- | ------ | ------ | -------------------- |
|      |        |        |                      |

35、is_serialized_string()

- 检查序列化数据是否为字符串类型：

```
$result = RC_Format::is_serialized_string($data);
```

| 1    | $data | string | 序列化数据 |
| ---- | ----- | ------ | ---------- |
|      |       |        |            |

36、maybe_serialize()

- 序列化数据（如果需要）：

```
$result = RC_Format::maybe_serialize($data);
```

| 1    | $data | array\|object | 可能序列化的数据 |
| ---- | ----- | ------------- | ---------------- |
|      |       |               |                  |

37、maybe_unserialize()

- 仅当值被序列化时才将其非序列化：

```
$result = RC_Format::maybe_unserialize($original);
```

| 1    | $original | string | 如果需要，可能是非序列化的原始版本 |
| ---- | --------- | ------ | ---------------------------------- |
|      |           |        |                                    |

38、is_serialized()

- 检查值以确定是否已序列化：

```
$result = RC_Format::is_serialized($data, $strict = true);
```

| 1    | $data   | string | 要检查是否已序列化的值                     |
| ---- | ------- | ------ | ------------------------------------------ |
| 2    | $strict | bool   | 可选的。是否对字符串的结尾严格。默认为真。 |

39、removeEmoji()

- 删除Emoji：

```
$result = RC_Format::removeEmoji($text);
```

| 1    | $text | string | 内容 |
| ---- | ----- | ------ | ---- |
|      |       |        |      |

40、filterEmoji()

- 过滤Emoji：

```
$result = RC_Format::filterEmoji($str);
```

| 1    | $str | string | 内容 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |