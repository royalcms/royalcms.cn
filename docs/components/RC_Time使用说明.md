### ecjia后台RC_Time使用说明



#### 方法列表

| 编号 |      方法名       |                简单描述                 |
| :--: | :---------------: | :-------------------------------------: |
|  1   |     gmtime()      |      获得当前格林威治时间的时间戳       |
|  2   | local_strtotime() | 将一个用户自定义时区的日期转为GMT时间戳 |
|  3   |   local_date()    |  将GMT时间戳格式化为用户自定义时区日期  |
|  4   |  local_mktime()   |  生成一个用户自定义时区日期的GMT时间戳  |

#### 方法详细说明

1、gmtime()

- 获得当前格林威治时间的时间戳，调用示例：

```
RC_Time::gmtime()
```

2、local_strtotime()

- 将一个用户自定义时区的日期转为GMT时间戳，调用示例：

```
RC_Time::local_strtotime($str, $now = null)
```

| 1    | $str | string | 用户自定义时区的日期    |
| ---- | ---- | ------ | ----------------------- |
| 2    | $now | string | GMT时间戳（默认为null） |

3、local_date()

- 将一个用户自定义时区的日期转为GMT时间戳，调用示例：

```
RC_Time::local_date($format, $time = null)
```

| 1    | $format | string | 自定义时区格式          |
| ---- | ------- | ------ | ----------------------- |
| 2    | $time   | string | GMT时间戳（默认为null） |

4、local_mktime()

- 将一个用户自定义时区的日期转为GMT时间戳，调用示例：

```
RC_Time::local_mktime($hour = NULL, $minute = NULL, $second = NULL, $month = NULL, $day = NULL, $year = NULL)
```

| 1    | $hour   | int  | 自定义小时，默认为空 |
| ---- | ------- | ---- | -------------------- |
| 2    | $minute | int  | 自定义分钟，默认为空 |
| 3    | $minute | int  | 自定义秒，默认为空   |
| 4    | $minute | int  | 自定义月，默认为空   |
| 5    | $minute | int  | 自定义日，默认为空   |
| 6    | $minute | int  | 自定义年，默认为空   |