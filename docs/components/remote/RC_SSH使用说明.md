### ECJia后台RC_SSH使用说明

##### 方法列表

| 编号 |   方法名    |             简单描述             |
| :--: | :---------: | :------------------------------: |
|  1   |  define()   |     将一组命令定义为一项任务     |
|  2   |   task()    |         针对连接运行任务         |
|  3   |    run()    |       针对连接运行一组命令       |
|  4   |    get()    |        下载远程文件的内容        |
|  5   | getString() |        获取远程文件的内容        |
|  6   |    put()    |      将本地文件上传到服务器      |
|  7   | putString() | 将字符串上传到服务器上的给定文件 |
|  8   |  exists()   |  检查服务器上是否存在给定的文件  |
|  9   |  rename()   |          重命名远程文件          |
|  10  |  delete()   |      从服务器中删除远程文件      |

#### 方法详细说明

1、define

- 将一组命令定义为一项任务

  ```
  RC_SSH::define($task, $commands);
  ```

  | 1    | $task     | String | 任务名                 |
  | ---- | --------- | ------ | ---------------------- |
  | 2    | $commands | array  | 服务器执行的 Bash code |

2、task()

- 针对连接进行任务

  ```
  RC_SSH::task($task, Closure $callback = null);
  ```

  | 1    | $task     | String   | 任务名 |
  | ---- | --------- | -------- | ------ |
  | 2    | $callback | \Closure | 回调值 |

3、run()

- 针对连接运行一组命令

  ```
  RC_SSH::run($commands, Closure $callback = null);
  ```

  | 1    | $commands | Array    | 服务器执行的 Bash code |
  | ---- | --------- | -------- | ---------------------- |
  | 2    | $callback | \Closure | 回调值                 |

4、slabs()

- 下载远程的内容

  ```
  RC_SSH::get($remote, $local);
  ```

  | 1    | $remote | String | 远程文件地址 |
  | ---- | ------- | ------ | ------------ |
  | 2    | $local  | String | 本地文件地址 |

5、getString()

- 获取远程文件的内容

  ```
  RC_SSH::getString($remote));
  ```

  | 1    | $remote | String | 远程文件地址 |
  | ---- | ------- | ------ | ------------ |
  |      |         |        |              |

6、put()

- 将本地文件上传到服务器

  ```
  RC_SSH::put($local, $remote);
  ```

  | 1    | $local  | String | 本地文件地址 |
  | ---- | ------- | ------ | ------------ |
  | 2    | $remote | String | 远程文件地址 |

7、putString()

- 将字符串上传到服务器上的给定文件

  ```
  RC_SSH::putString($remote, $contents);
  ```

  | 1    | $remote   | String | 远程文件地址 |
  | ---- | --------- | ------ | ------------ |
  | 2    | $contents | String | 字符串内容   |

8、exists()

- 检查服务器上是否存在给定的文件

  ```
  RC_SSH::exists($remote);
  ```

  | 1    | $remote | String | 远程文件地址 |
  | ---- | ------- | ------ | ------------ |
  |      |         |        |              |

9、rename()

- 重命名远程文件

  ```
  RC_SSH::rename($remote, $newRemote);
  ```

  | 1    | $remote    | String | 远程文件地址     |
  | ---- | ---------- | ------ | ---------------- |
  | 2    | $newRemote | String | 新的远程文件地址 |

10、delete()

- 从服务器中删除远程文件

  ```
  RC_SSH::delete($remote);
  ```

  | 1    | $remote | String | 远程文件地址 |
  | ---- | ------- | ------ | ------------ |
  |      |         |        |              |