### ECJiaWiki:Ecjia后台RC Style使用说明

#### 方法列表

| 编号 |      方法名称      |             简单描述              |
| :--: | :----------------: | :-------------------------------: |
|  1   |   print_styles()   |     显示$handles队列中的样式      |
|  2   | add_inline_style() |  为注册的样式表添加额外的CSS样式  |
|  3   |  register_style()  |           注册CSS样式表           |
|  4   | deregister_style() |        删除已注册的样式表         |
|  5   |  enqueue_style()   |        将CSS样式表排入队列        |
|  6   |  dequeue_style()   |       删除以前CSS样式表队列       |
|  7   |     style_is()     | 检查是否已将CSS样式表添加到队列中 |
|  8   |  style_add_data()  |      将元数据添加到CSS样式表      |

#### 方法详细说明

print_styles()

- 显示$handles队列中的样式：

```
$styles = RC_Style::print_styles($handles = false);
```

| 1    | $handles | bool | 要打印的样式。 默认为'false'。 |
| ---- | -------- | ---- | ------------------------------ |
|      |          |      |                                |

add_inline_style()

- 为注册的样式表添加额外的CSS样式：

```
$result = RC_Style::add_inline_style($handle, $data);
```

| 1    | $handles | string | 要添加额外样式的样式表的名称。 一定是小写的。 |
| ---- | -------- | ------ | --------------------------------------------- |
| 2    | $data    | string | 包含要添加的CSS样式的字符串。                 |

register_style()

- 注册CSS样式表：

```
RC_Style::register_style($handle, $src, $deps = array(), $ver = false, $media = 'all');
```

| 1    | string | $handles | 样式表的名称。                                               |
| ---- | ------ | -------- | ------------------------------------------------------------ |
| 2    | $src   | bool     | Royalcms系统根目录中样式表的路径。                           |
| 3    | $deps  | array    | 此样式表所依赖的已注册样式处理数组。 默认空数组。            |
| 4    | $ver   | bool     | 指定样式表版本号的字符串。 用于确保无论缓存如何都将正确的版本发送到客户端。 默认为'false'。 |
| 5    | $media | string   | 已定义此样式表的媒体。 默认为“all”。                         |

deregister_style()

- 删除已注册的样式表：

```
RC_Style::deregister_style($handle);
```

| 1    | $handles | string | 要删除的样式表的名称。 |
| ---- | -------- | ------ | ---------------------- |
|      |          |        |                        |

enqueue_style()

- 将CSS样式表排入队列：

```
RC_Style::enqueue_style($handle, $src = false, $deps = array(), $ver = false, $media = 'all');
```

| 1    | $handles | string | 样式表的名称。                                               |
| ---- | -------- | ------ | ------------------------------------------------------------ |
| 2    | $src     | bool   | Royalcms系统根目录中样式表的路径。                           |
| 3    | $deps    | array  | 此样式表所依赖的已注册样式处理数组。 默认空数组。            |
| 4    | $ver     | bool   | 指定样式表版本号的字符串。 用于确保无论缓存如何都将正确的版本发送到客户端。 默认为'false'。 |
| 5    | $media   | string | 已定义此样式表的媒体。 默认为“all”。                         |

dequeue_style()

- 删除以前CSS样式表队列：

```
RC_Style::dequeue_style($handle);
```

| 1    | $handles | string | 要删除的样式表的名称。 |
| ---- | -------- | ------ | ---------------------- |
|      |          |        |                        |

style_is()

- 检查是否已将CSS样式表添加到队列中：

```
$result = RC_Style::style_is($handle, $list = 'enqueued');
```

| 1    | $handles | string | 样式表的名称。                                   |
| ---- | -------- | ------ | ------------------------------------------------ |
| 2    | $list    | string | 可选的。 要检查的样式表的状态。 默认'enqueued'。 |

style_add_data()

- 将元数据添加到CSS样式表：

```
$result = RC_Style::style_add_data($handle, $key, $value);
```

| 1    | $handles | string | 样式表的名称。                |
| ---- | -------- | ------ | ----------------------------- |
| 2    | $key     | string | 我们存储值的数据点的名称。    |
| 2    | $value   | mixed  | 包含要添加的CSS数据的字符串。 |