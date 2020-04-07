### ECJiaWiki:Ecjia后台RC Session使用说明

##### 方法列表

| 编号 |    方法名    |                        简单描述                         |
| :--: | :----------: | :-----------------------------------------------------: |
|  1   |    get()     |                        获取数据                         |
|  2   |    all()     |                  获取所有 Session 数据                  |
|  3   |    has()     | 判断 Session 中是否存在某个值，值存在且不为null返回true |
|  4   |   exists()   |      判断 Session 中是否存在某个值，值存在返回true      |
|  5   |    put()     |                        存储数据                         |
|  6   |    push()    |                在 Session 数组中保存数据                |
|  7   |    pull()    |             从 Session 检索并且删除一个项目             |
|  8   |   flash()    |            闪存数据，主要用于短期的状态消息             |
|  9   |  reflash()   |                   保留所有的闪存数据                    |
|  10  |    keep()    |                   保留特定的闪存数据                    |
|  11  |   forget()   |                从 Session 内删除一条数据                |
|  12  |   flush()    |                 删除 Session 内所有数据                 |
|  13  | regenerate() |                   重新生成 Session ID                   |

#### 方法详细说明

1、get

- 获取数据

  ```
  RC_Session::get($key, $default);
  ```

  | 1    | $key     | String | Session键          |
  | ---- | -------- | ------ | ------------------ |
  | 2    | $default | String | 默认值（不是必填） |

2、all()

- 获取所有 Session 数据

  ```
  RC_Session::all();
  ```

3、has()

- 判断 Session 中是否存在某个值，如果该值存在且不为 null，那么 has 方法会返回 true。

  ```
  RC_Session::has($key);
  ```

  | 1    | $key | String | Session键 |
  | ---- | ---- | ------ | --------- |
  |      |      |        |           |

4、exists()

- 判断 Session 中是否存在某个值，值存在返回true

  ```
  RC_Session::exists($key);
  ```

  | 1    | $key | String | Session键 |
  | ---- | ---- | ------ | --------- |
  |      |      |        |           |

5、put()

- 存储数据

  ```
  RC_Session::put($key, $value));
  ```

  | 1    | $key   | String | Session键 |
  | ---- | ------ | ------ | --------- |
  | 2    | $value | String | 值        |

6、push()

- 在 Session 数组中保存数据

  ```
  RC_Session::push($arraykey, $value);
  ```

  | 1    | $arraykey | array  | Session 数组 |
  | ---- | --------- | ------ | ------------ |
  | 2    | $value    | String | 值           |

7、pull()

- 从 Session 检索并且删除一个项目

  ```
  RC_Session::pull($remote, $contents);
  ```

  | 1    | $key | String | Session键 |
  | ---- | ---- | ------ | --------- |
  |      |      |        |           |

8、flash()

- 闪存数据，主要用于短期的状态消息

  ```
  RC_Session::flash($key, $value);
  ```

  | 1    | $key   | String | Session键 |
  | ---- | ------ | ------ | --------- |
  | 2    | $value | String | 值        |

9、reflash()

- 保留所有的闪存数据

  ```
  RC_Session::reflash();
  ```

10、keep()

- 保留特定的闪存数据

  ```
  RC_Session::keep($array);
  ```

  | 1    | $array | array | Session集合 |
  | ---- | ------ | ----- | ----------- |
  |      |        |       |             |

11、forget()

- 从 Session 内删除一条数据

  ```
  RC_Session::forget($key);
  ```

  | 1    | $key | String | Session键 |
  | ---- | ---- | ------ | --------- |
  |      |      |        |           |

12、flush()

- 删除 Session 内所有数据

  ```
  RC_Session::flush();
  ```


13、regenerate()

- 重新生成 Session ID

  ```
  RC_Session::regenerate();
  ```