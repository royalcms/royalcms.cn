### ECJiaWiki:Ecjia后台RC Script使用说明

#### 方法列表

| 编号 |      方法名称       |              简单描述              |
| :--: | :-----------------: | :--------------------------------: |
|  1   |   print_scripts()   | 在$handles队列中的文档头中打印脚本 |
|  2   |  register_script()  |           注册一个新脚本           |
|  3   |  localize_script()  |             本地化脚本             |
|  4   | deregister_script() |          删除已注册的脚本          |
|  5   |  enqueue_script()   |              脚本队列              |
|  6   |  dequeue_script()   |          删除以前脚本队列          |
|  7   |     script_is()     |     检查脚本是否已添加到队列中     |

#### 方法详细说明

print_scripts()

- 在$handles队列中的文档头中打印脚本

```
$scripts = RC_Script::print_scripts($handles = false);
```

| 1    | $handles | bool | 要打印的脚本。 默认为'false'。 |
| ---- | -------- | ---- | ------------------------------ |
|      |          |      |                                |

register_script()

- 注册一个新脚本：

```
RC_Script::register_script($handle, $src, $deps = array(), $ver = false, $in_footer = false)
```

| 1    | $handles   | string | 脚本的名称。                                                 |
| ---- | ---------- | ------ | ------------------------------------------------------------ |
| 2    | $src       | bool   | Royalcms系统根目录中脚本的路径。                             |
| 3    | $deps      | array  | 此脚本依赖的注册脚本数组。 如果没有依赖项，则设置为false。 默认空数组。 |
| 4    | $ver       | bool   | 指定脚本版本号的字符串。 它作为查询字符串连接到路径末尾。 默认为'false'。 |
| 5    | $in_footer | bool   | 是否在</head>之前或</body>之前将脚本入队。 默认为“false”。   |

localize_script()

- 本地化脚本：

```
RC_Script::localize_script($handle, $object_name, $l10n)
```

| 1    | $handles     | string | 脚本句柄将附加数据。                                        |
| ---- | ------------ | ------ | ----------------------------------------------------------- |
| 2    | $object_name | string | JavaScript对象的名称。 直接传递，所以它应该是合格的JS变量。 |
| 3    | $l10n        | array  | 数据本身。 数据可以是单个或多维数组。                       |

deregister_script()

- 删除已注册的脚本：

```
RC_Script::deregister_script($handle)
```

| 1    | $handles | string | 要删除的脚本的名称。 |
| ---- | -------- | ------ | -------------------- |
|      |          |        |                      |

enqueue_script()

- 脚本队列：

```
RC_Script::enqueue_script($handle, $src = false, $deps = array(), $ver = false, $in_footer = false)
```

| 1    | $handles   | string | 脚本的名称。                                                 |
| ---- | ---------- | ------ | ------------------------------------------------------------ |
| 2    | $src       | bool   | Royalcms系统根目录中脚本的路径。                             |
| 3    | $deps      | array  | 此脚本依赖的注册脚本数组。 如果没有依赖项，则设置为false。 默认空数组。 |
| 4    | $ver       | bool   | 指定脚本版本号的字符串。 它作为查询字符串连接到路径末尾。 默认为'false'。 |
| 5    | $in_footer | bool   | 是否在</head>之前或</body>之前将脚本入队。 默认为“false”。   |

dequeue_script()

- 脚本队列：

```
RC_Script::dequeue_script($handle)
```

| 1    | $handles | string | 要删除的脚本的名称。 |
| ---- | -------- | ------ | -------------------- |
|      |          |        |                      |

script_is()

- 脚本队列：

```
$result = RC_Script::script_is($handle, $list = 'enqueued')
```

| 1    | $handles | string | 脚本的名称。                                   |
| ---- | -------- | ------ | ---------------------------------------------- |
| 2    | $list    | bool   | 可选的。 要检查的脚本的状态。 默认'enqueued'。 |