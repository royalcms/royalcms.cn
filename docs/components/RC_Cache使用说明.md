### ecjia后台RC_Cache使用说明



#### 方法列表

| 编号 |        方法名称         |       简单描述       |
| :--: | :---------------------: | :------------------: |
|  1   |     app_cache_set()     | 快速设置APP缓存数据  |
|  2   |     app_cache_get()     | 快速获取APP缓存数据  |
|  3   |   app_cache_delete()    | 快速删除APP缓存数据  |
|  4   |  userdata_cache_set()   | 快速存储用户个人数据 |
|  5   |  userdata_cache_get()   | 快速读取用户个人数据 |
|  6   | userdata_cache_delete() | 快速删除用户个人数据 |
|  7   |    table_cache_set()    |    设置数据表缓存    |
|  8   |    table_cache_get()    |    获取数据表缓存    |
|  9   |  table_cache_delete()   |    删除数据表缓存    |
|  10  |    query_cache_set()    |     设置查询缓存     |
|  11  |    query_cache_get()    |     获取查询缓存     |
|  12  |  query_cache_delete()   |     删除查询缓存     |

#### 方法详细说明

1、app_cache_set()

- 快速设置APP缓存数据，可以使用RC_Cache::app_cache_set()进行调用。

```
  public static function app_cache_set($name, $data, $app, $expire = null)
```

| 1    | $name   | string | 缓存文件的名称       |
| ---- | ------- | ------ | -------------------- |
| 2    | $data   | string | 需要缓存的数据       |
| 3    | $app    | string | app应用名称          |
| 4    | $expire | int    | 缓存时间（不是必填） |

2、app_cache_get()

- 快速获取APP缓存数据，可以使用RC_Cache::app_cache_get()进行调用。

```
  public static function app_cache_get($name, $app)
```

| 1    | $name | string | 缓存文件的名称 |
| ---- | ----- | ------ | -------------- |
| 2    | $data | string | app应用名称    |

3、app_cache_delete()

- 快速删除APP缓存数据，可以使用RC_Cache::app_cache_delete()进行调用。

```
  public static function app_cache_delete($name, $app)
```

| 1    | $name | string | 缓存文件的名称 |
| ---- | ----- | ------ | -------------- |
| 2    | $data | string | app应用名称    |

4、userdata_cache_set()

- 快速存储用户个人数据，可以使用RC_Cache::userdata_cache_set()进行调用。

```
  public static function userdata_cache_set($name, $data, $userid, $isadmin = false, $expire = null)
```

| 1    | $name    | string | 缓存文件的名称                                        |
| ---- | -------- | ------ | ----------------------------------------------------- |
| 2    | $data    | string | 需要存储的个人数据                                    |
| 3    | $userid  | int    | 用户id                                                |
| 4    | $isadmin | bool   | 是否为管理员，$isadmin = false不是，$isadmin = true是 |
| 5    | $expire  | int    | 缓存时间（不是必填）                                  |

5、userdata_cache_get()

- 快速读取用户个人数据，可以使用RC_Cache::userdata_cache_get()进行调用。

```
 public static function userdata_cache_get($name, $userid, $isadmin = false, $expire = null)
```

| 1    | $name    | string | 缓存文件的名称                                        |
| ---- | -------- | ------ | ----------------------------------------------------- |
| 2    | $userid  | int    | 用户id                                                |
| 3    | $isadmin | bool   | 是否为管理员，$isadmin = false不是，$isadmin = true是 |
| 4    | $expire  | int    | 缓存时间（不是必填）                                  |

6、userdata_cache_delete()

- 快速删除用户个人数据，可以使用RC_Cache::userdata_cache_delete()进行调用。

```
 public static function userdata_cache_delete($name, $userid, $isadmin = false, $expire = null)
```

| 1    | $name    | string | 缓存文件的名称                                        |
| ---- | -------- | ------ | ----------------------------------------------------- |
| 2    | $userid  | int    | 用户id                                                |
| 3    | $isadmin | bool   | 是否为管理员，$isadmin = false不是，$isadmin = true是 |
| 4    | $expire  | int    | 缓存时间（不是必填）                                  |

7、table_cache_set()

- 设置数据表缓存，可以使用RC_Cache::table_cache_set()进行调用。

```
 public static function table_cache_set($name, $data, $expire = null)
```

| 1    | $name   | string | 数据表名称           |
| ---- | ------- | ------ | -------------------- |
| 2    | $data   | string | 需要缓存的内容       |
| 3    | $expire | int    | 缓存时间（不是必填） |

8、table_cache_get()

- 获取数据表缓存，可以使用RC_Cache::table_cache_get()进行调用。

```
 public static function table_cache_get($name)
```

| 1    | $name | string | 数据表名称 |
| ---- | ----- | ------ | ---------- |
|      |       |        |            |

9、table_cache_delete()

- 删除数据表缓存，可以使用RC_Cache::table_cache_delete()进行调用。

```
 public static function table_cache_delete($name)
```

| 1    | $name | string | 数据表名称 |
| ---- | ----- | ------ | ---------- |
|      |       |        |            |

10、query_cache_set()

- 设置查询缓存，可以使用RC_Cache::query_cache_set()进行调用。

```
 public static function query_cache_set($name, $data, $expire = null)
```

| 1    | $name   | string | 缓存文件名称         |
| ---- | ------- | ------ | -------------------- |
| 2    | $data   | string | 缓存数据             |
| 3    | $expire | int    | 缓存时间（不是必填） |

11、query_cache_get()

- 获取查询缓存，可以使用RC_Cache::query_cache_get()进行调用。

```
 public static function query_cache_get($name)
```

| 1    | $name | string | 缓存文件名称 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |

12、query_cache_delete()

- 删除查询缓存，可以使用RC_Cache::query_cache_delete()进行调用。

```
 public static function query_cache_delete($name)
```

| 1    | $name | string | 缓存文件名称 |
| ---- | ----- | ------ | ------------ |
|      |       |        |              |