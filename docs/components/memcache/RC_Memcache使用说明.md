### Ecjia后台RC_Memcache使用说明

##### 方法列表

| 编号 |   方法名    |                 简单描述                  |
| :--: | :---------: | :---------------------------------------: |
|  1   |   stats()   |          获取服务器池的统计信息           |
|  2   | settings()  |         发送统计设置命令到服务器          |
|  3   |   sizes()   |           发送sizes命令到服务器           |
|  4   |   slabs()   |             获取SLABS统计信息             |
|  5   |   items()   | 发送stats item命令到服务器以检索SLABS项目 |
|  6   |    get()    |              获取给定的项目               |
|  7   |    add()    |              设置给定的项目               |
|  8   |    set()    |              写入给定的项目               |
|  9   |  replace()  |              替换给定的项目               |
|  10  |  delete()   |              删除给定的项目               |
|  11  | increment() |             递增给定的配置值              |
|  12  | decrement() |             递减给定的配置值              |
|  13  |   flush()   |           刷新所有给定的配置值            |
|  14  |  search()   |              搜索给定的项目               |
|  15  |  telnet()   |         在服务器上执行Telnet命令          |

#### 方法详细说明

1、 stats()

- 获取服务器池的统计信息

  ```
  RC_Memcache::stats($server,$port);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |

2、settings()

- 发送统计设置命令到服务器

  ```
  RC_Memcache::settings($server,$port);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |

3、sizes()

- 发送sizes命令到服务器

  ```
  RC_Memcache::sizes($server,$port);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |

4、slabs()

- 获取SLABS统计信息

  ```
  RC_Memcache::slabs($server,$port);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |

5、items()

- 发送stats item命令到服务器以检索SLABS项目

  ```
  RC_Memcache::items($server,$port,$slab);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |
  | 3    | $slab   | Interger | slab的id |

6、get()

- 获取给定的项目

  ```
  RC_Memcache::get($server,$port,$key);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |
  | 3    | $key    | String   | 检索的值 |

7、add()

- 设置给定的项目

  ```
  RC_Memcache::add($server,$port,$key,$data,$duration);
  ```

  | 1    | $server   | String   | 主机名       |
  | ---- | --------- | -------- | ------------ |
  | 2    | $port     | Interger | 主机端口     |
  | 3    | $key      | String   | 存储的值     |
  | 4    | $data     | Mixed    | 要存储的数据 |
  | 5    | $duration | Interger | 持续时间     |

8、set()

- 写入给定的项目

  ```
  RC_Memcache::set($server,$port,$key,$data,$duration);
  ```

  | 1    | $server   | String   | 主机名       |
  | ---- | --------- | -------- | ------------ |
  | 2    | $port     | Interger | 主机端口     |
  | 3    | $key      | String   | 存储的值     |
  | 4    | $data     | Mixed    | 要存储的数据 |
  | 5    | $duration | Interger | 持续时间     |

9、replace()

- 替换给定的项目

  ```
  RC_Memcache::replace($server,$port,$key,$data,$duration);
  ```

  | 1    | $server   | String   | 主机名       |
  | ---- | --------- | -------- | ------------ |
  | 2    | $port     | Interger | 主机端口     |
  | 3    | $key      | String   | 存储的值     |
  | 4    | $data     | Mixed    | 要存储的数据 |
  | 5    | $duration | Interger | 持续时间     |

10、delete()

- 删除给定的项目

  ```
  RC_Memcache::delete($server,$port,$key);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |
  | 3    | $key    | String   | 删除的值 |

11、increment()

- 递增给定的配置值

  ```
  RC_Memcache::increment($server,$port,$key,$value);
  ```

  | 1    | $server | String   | 主机名       |
  | ---- | ------- | -------- | ------------ |
  | 2    | $port   | Interger | 主机端口     |
  | 3    | $key    | String   | 自增的值     |
  | 4    | $value  | Integer  | 要自增的数据 |

12、decrement()

- 刷新所有给定的配置值

  ```
  RC_Memcache::decrement($server,$port,$key,$value);
  ```

  | 1    | $server | String   | 主机名       |
  | ---- | ------- | -------- | ------------ |
  | 2    | $port   | Interger | 主机端口     |
  | 3    | $key    | String   | 自减的值     |
  | 4    | $value  | Integer  | 要自减的数据 |

13、flush()

- 刷新所有给定的配置值

  ```
  RC_Memcache::flush($server,$port,$delay);
  ```

  | 1    | $server | String   | 主机名               |
  | ---- | ------- | -------- | -------------------- |
  | 2    | $port   | Interger | 主机端口             |
  | 3    | $delay  | Integer  | 刷新服务器之前的延迟 |

14、search()

- 搜索给定的项目

  ```
  RC_Memcache::search($server,$port,$search);
  ```

  | 1    | $server | String   | 主机名   |
  | ---- | ------- | -------- | -------- |
  | 2    | $port   | Interger | 主机端口 |
  | 3    | $search | String   | 搜索的值 |

15、telnet()

- 在服务器上执行Telnet命令

  ```
  RC_Memcache::telnet($server,$port,$command);
  ```

  | 1    | $server | String   | 主机名       |
  | ---- | ------- | -------- | ------------ |
  | 2    | $port   | Interger | 主机端口     |
  | 3    | $delay  | Integer  | 要执行的命令 |