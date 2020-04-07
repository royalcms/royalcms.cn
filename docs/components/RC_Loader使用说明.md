### ecjia后台RC_Loader使用说明

#### 方法列表

| 编号 |       方法名称       |                       简单描述                       |
| :--: | :------------------: | :--------------------------------------------------: |
|  1   |   load_sys_class()   |                    加载系统类方法                    |
|  2   |   load_app_class()   |                    加载应用类方法                    |
|  3   | load_plugin_class()  |                    加载插件类方法                    |
|  4   |      my_path()       |                 是否有自己的扩展文件                 |
|  5   |     load_model()     |                     加载数据模型                     |
|  6   |   load_sys_model()   |                   加载系统数据模型                   |
|  7   |   load_app_model()   |                   加载应用数据模型                   |
|  8   |    load_module()     |                    加载系统模块库                    |
|  9   |  load_app_module()   |                    加载应用模块库                    |
|  10  |  load_app_config()   |                   加载应用配置文件                   |
|  11  |  load_sys_config()   |                   加载系统配置文件                   |
|  12  | load_plugin_config() |                   加载插件配置文件                   |
|  13  |   load_app_lang()    |                   加载应用语言文件                   |
|  14  |   load_sys_lang()    |                   加载系统语言文件                   |
|  15  |  load_plugin_lang()  |                   加载插件语言文件                   |
|  16  |  load_theme_lang()   |                   加载主题语言文件                   |
|  17  |   load_sys_func()    |                   加载系统的函数库                   |
|  18  |   load_app_func()    |                    加载应用函数库                    |
|  19  |   auto_load_func()   |             自动加载autoload目录下函数库             |
|  20  |      load_api()      |                       加载api                        |
|  21  |    load_vendor()     |                      加载vemdor                      |
|  22  |     load_theme()     |                      加载theme                       |
|  23  |  exists_site_app()   |    判断是否存在同名的站点APP，站点APP具体优先使用    |
|  24  | exists_site_plugin() | 判断是否存在同名的站点PLUGIN，站点PLUGIN具体优先使用 |
|  25  | exists_site_system() | 判断是否存在同名的站点System，站点System具体优先使用 |

#### 方法详细说明

1、load_sys_class()

- 加载系统类方法：

```
RC_Loader::load_sys_class($classname, $initialize = true);
```

| 1    | $classname  | string | 类名       |
| ---- | ----------- | ------ | ---------- |
| 2    | $initialize | intger | 是否初始化 |

2、load_app_class()

- 加载应用类方法：

```
RC_Loader::load_app_class($classname, $m = null, $initialize = true);
```

| 1    | $classname   | string | 类名       |
| ---- | ------------ | ------ | ---------- |
| 2    | $m           | string | 模块       |
| 3    | $$initialize | intger | 是否初始化 |

3、load_plugin_class()

- 加载插件类方法：

```
RC_Loader::load_app_class($classname, $plugin_dir, $initialize = true);
```

| 1    | $classname  | string | 类名       |
| ---- | ----------- | ------ | ---------- |
| 2    | $plugin_dir | string | 模块       |
| 3    | $initialize | intger | 是否初始化 |

4、my_path()

- 是否有自己的扩展文件：

```
RC_Loader::my_path($filepath);
```

| 1    | $filepath | string | 路径 |
| ---- | --------- | ------ | ---- |
|      |           |        |      |

5、load_model()

- 加载数据模型：

```
$db = RC_Loader::load_model($classname);
```

| 1    | $classname | string | 类名 |
| ---- | ---------- | ------ | ---- |
|      |            |        |      |

6、load_sys_model()

- 加载系统数据模型：

```
$db = RC_Loader::load_sys_model($classname);
```

| 1    | $classname | string | 类名 |
| ---- | ---------- | ------ | ---- |
|      |            |        |      |

7、load_app_model()

- 加载应用数据模型：

```
$db = RC_Loader::load_app_model($classname, $m = '');
```

| 1    | $classname | string | 类名 |
| ---- | ---------- | ------ | ---- |
| 2    | $m         | string | 模块 |

8、load_module()

- 加载系统模块库：

```
$handle = RC_Loader::load_module($classname, $initialize = true);
```

| 1    | $classname   | string | 类名       |
| ---- | ------------ | ------ | ---------- |
| 2    | $$initialize | intger | 是否初始化 |

9、load_app_module()

- 加载应用模块库：

```
$handle = RC_Loader::load_app_module($classname, $m = '', $initialize = true);
```

| 1    | $classname  | string | 类名       |
| ---- | ----------- | ------ | ---------- |
| 2    | $plugin_dir | string | 模块       |
| 3    | $initialize | intger | 是否初始化 |

10、load_app_config()

- 加载应用配置文件：

```
RC_Loader::load_app_config($cfgname, $m = '');
```

| 1    | $cfgname | string | 配置文件名 |
| ---- | -------- | ------ | ---------- |
| 2    | $m       | string | 模块       |

11、load_sys_config()

- 加载系统配置文件：

```
$modules = RC_Loader::load_sys_config($cfgname, $m = '');
```

| 1    | $cfgname | string | 配置文件名 |
| ---- | -------- | ------ | ---------- |
| 2    | $m       | string | 模块       |

12、load_plugin_config()

- 加载插件配置文件：

```
$modules = RC_Loader::load_plugin_config($cfgname, $m = '');
```

| 1    | $cfgname | string | 配置文件名 |
| ---- | -------- | ------ | ---------- |
| 2    | $m       | string | 模块       |

13、load_app_lang()

- 加载应用语言文件：

```
RC_Loader::load_app_lang($filename, $m = '');
```

| 1    | $filename | string | 文件名 |
| ---- | --------- | ------ | ------ |
| 2    | $m        | mixed  | 模块   |

14、load_sys_lang()

- 加载系统语言文件：

```
RC_Loader::load_sys_lang($filename);
```

| 1    | $filename | string | 文件名 |
| ---- | --------- | ------ | ------ |
|      |           |        |        |

15、load_plugin_lang()

- 加载插件语言文件：

```
RC_Loader::load_plugin_lang($filename, $m = '');
```

| 1    | $filename | string | 文件名 |
| ---- | --------- | ------ | ------ |
| 2    | $m        | mixed  | 模块   |

16、load_theme_lang()

- 加载主题语言文件：

```
RC_Loader::load_theme_lang($filename);
```

| 1    | $filename | string | 文件名 |
| ---- | --------- | ------ | ------ |
|      |           |        |        |

17、load_sys_func()

- 加载系统的函数库：

```
RC_Loader::load_sys_func($func);
```

| 1    | $func | string | 函数库名 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

18、load_app_func()

- 加载应用函数库：

```
RC_Loader::load_app_func($func, $m = '');
```

| 1    | $func | string | 函数库名 |
| ---- | ----- | ------ | -------- |
| 2    | $m    | mixed  | 模块     |

19、auto_load_func()

- 自动加载autoload目录下函数库：

```
RC_Loader::auto_load_func($path = '');
```

| 1    | $path | string | 目录路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

20、load_api()

- 加载api：

```
RC_Loader::load_api($api_key, $parms = array());
```

| 1    | $api_key | string | api密钥 |
| ---- | -------- | ------ | ------- |
| 2    | $parms   | array  | 参数    |

21、load_vendor()

- 加载vemdor：

```
RC_Loader::load_vendor($filename);
```

| 1    | $filename | string | 类名 eg: RC_Loader::load_vendor('smarty/Smarty.class') |
| ---- | --------- | ------ | ------------------------------------------------------ |
|      |           |        |                                                        |

22、load_theme()

- 加载theme：

```
RC_Loader::load_theme($filename);
```

| 1    | $filename | string | 模板目录下文件路径和文件名 |
| ---- | --------- | ------ | -------------------------- |
|      |           |        |                            |

23、exists_site_app()

- 判断是否存在同名的站点APP，站点APP具体优先使用:

```
RC_Loader::exists_site_app($m);
```

| 1    | $m   | string | 模块 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

24、exists_site_plugin()

- 判断是否存在同名的站点PLUGIN，站点PLUGIN具体优先使用：

```
RC_Loader::exists_site_plugin($dir);
```

| 1    | $file | string | 目录 |
| ---- | ----- | ------ | ---- |
|      |       |        |      |

25、exists_site_system()

- 判断是否存在同名的站点System，站点System具体优先使用：

```
RC_Loader::exists_site_system();
```