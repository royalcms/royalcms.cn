### Ecjia后台RC_Error使用说明



#### 方法列表

| 编号 |      方法名称       |         简单描述         |
| :--: | :-----------------: | :----------------------: |
|  1   | get_error_message() |     获取单个错误信息     |
|  2   |     add_data()      |    为错误代码添加信息    |
|  3   |     is_error()      | 判断是否是Royalcms Error |

#### 方法详细说明

1、get_error_message()

- 获取单个错误信息

2、add_data()

- 为错误代码添加信息，调用示例：

```
RC_Error::add_data($data, $code);
```

| 1    | $data | mixed  | error data |
| ---- | ----- | ------ | ---------- |
| 2    | $code | string | error code |

3、is_error()

- 判断是否是Royalcms Error,调用示例：

```
RC_Error::is_error($thing);
```

| 1    | $thing | mixed | Check if unknown variable is a RC_Error object |
| ---- | ------ | ----- | ---------------------------------------------- |
|      |        |       |                                                |