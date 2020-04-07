### ecjia后台RC_Storage使用说明

#### 方法列表

| 编号 |       方法名称       |            简单描述            |
| :--: | :------------------: | :----------------------------: |
|  1   |        copy()        |            复制文件            |
|  2   |        move()        |            转移文件            |
|  3   |       delete()       |            删除文件            |
|  4   |       exists()       |        检测文件是否存在        |
|  5   |       mkdir()        |            创建目录            |
|  6   |       rmdir()        |            删除目录            |
|  7   | move_uploaded_file() |         转移上传的文件         |
|  8   |    get_contents()    |          获取文件内容          |
|  9   | get_contents_array() |        获取文件内容数组        |
|  10  |    put_contents()    |            写入内容            |
|  11  |        cwd()         |        获取当前工作目录        |
|  12  |       chdir()        |         改变当前的目录         |
|  13  |       chgrp()        |           改变文件组           |
|  14  |       chmod()        |          改变文件模式          |
|  15  |       chown()        |      改变指定文件的所有者      |
|  16  |       owner()        |      获取指定文件的所有者      |
|  17  |       group()        |          取得文件的组          |
|  18  |      is_file()       |         判断是否是文件         |
|  19  |       is_dir()       |         判断是否是目录         |
|  20  |    is_readable()     |          判断是否可读          |
|  21  |    is_writable()     |          判断是否可写          |
|  22  |       atime()        |   获取指定文件的上次访问时间   |
|  23  |       mtime()        |   获取文件内容上次的修改时间   |
|  24  |        size()        |       获取指定文件的大小       |
|  25  |       touch()        |  设置指定文件的访问和修改时间  |
|  26  |      dirlist()       |          获取目录列表          |
|  27  |      filelist()      | 获取目录下的指定类型的文件列表 |

#### 方法详细说明

1、copy()

- 复制文件，调用示例：

```
$disk = RC_Storage::disk();
$disk->copy($source, $destination, $overwrite = false, $mode = false);
```

| 1    | $source      | string  | 文件路径 |
| ---- | ------------ | ------- | -------- |
| 2    | $destination | string  | 文件路径 |
| 3    | $overwrite   | boolean | 是否覆盖 |
| 4    | $mode        | boolean | 模式     |

2、move()

- 转移文件，调用示例：

```
$disk = RC_Storage::disk();
$disk->move($source, $destination, $overwrite = false);
```

| 1    | $source      | string  | 文件路径 |
| ---- | ------------ | ------- | -------- |
| 2    | $destination | string  | 文件路径 |
| 3    | $overwrite   | boolean | 是否覆盖 |

3、delete()

- 删除文件，调用示例：

```
$disk = RC_Storage::disk();
$disk->delete($file, $recursive = false, $type = false);
```

| 1    | $file      | string  | 文件路径       |
| ---- | ---------- | ------- | -------------- |
| 2    | $recursive | boolean | 是否递归       |
| 3    | $type      | string  | 类型 文件/目录 |

4、exists()

- 检测文件是否存在，调用示例：

```
$disk = RC_Storage::disk();
$disk->exists($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

5、mkdir()

- 创建目录，调用示例：

```
$disk = RC_Storage::disk();
$disk->mkdir($path, $chmod = false, $chown = false, $chgrp = false);
```

| 1    | $path  | string  | 目录路径         |
| ---- | ------ | ------- | ---------------- |
| 2    | $chmod | boolean | 目录权限         |
| 3    | $chown | boolean | 改变文件所有者   |
| 4    | $chgrp | boolean | 改变文件所属的组 |

6、rmdir()

- 删除目录，调用示例：

```
$disk = RC_Storage::disk();
$disk->rmdir($path, $recursive = false);
```

| 1    | $path      | string  | 目录路径 |
| ---- | ---------- | ------- | -------- |
| 2    | $recursive | boolean | 是否递归 |

7、move_uploaded_file()

- 转移上传的文件，调用示例：

```
$disk = RC_Storage::disk();
$disk->move_uploaded_file($filename, $destination);
```

| 1    | $filename    | string | 文件名称 |
| ---- | ------------ | ------ | -------- |
| 2    | $destination | string | 文件路径 |

8、get_contents()

- 获取文件内容，调用示例：

```
$disk = RC_Storage::disk();
$disk->get_contents($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

9、get_contents_array()

- 获取文件内容数组，调用示例：

```
$disk = RC_Storage::disk();
$disk->get_contents_array($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

10、put_contents()

- 写入内容，调用示例：

```
$disk = RC_Storage::disk();
$disk->put_contents($file, $contents, $mode = false);
```

| 1    | $file     | string  | 文件路径 |
| ---- | --------- | ------- | -------- |
| 2    | $contents | string  | 内容     |
| 3    | $mode     | boolean | 模式     |

11、cwd()

- 获取当前工作目录，调用示例：

```
$disk = RC_Storage::disk();
$disk->cwd();
```

12、chdir()

- 改变当前的目录，调用示例：

```
$disk = RC_Storage::disk();
$disk->chdir($dir);
```

| 1    | $dir | string | 新的当前目录路径 |
| ---- | ---- | ------ | ---------------- |
|      |      |        |                  |

13、chgrp()

- 改变文件组，调用示例：

```
$disk = RC_Storage::disk();
$disk->chgrp($file, $group, $recursive = false);
```

| 1    | $file      | string  | 文件路径   |
| ---- | ---------- | ------- | ---------- |
| 2    | $group     | mixed   | 组名或数字 |
| 3    | $recursive | boolean | 是否递归   |

14、chmod()

- 改变文件模式，调用示例：

```
$disk = RC_Storage::disk();
$disk->chmod($file, $mode = false, $recursive = false);
```

| 1    | $file      | string  | 文件路径 |
| ---- | ---------- | ------- | -------- |
| 2    | $mode      | boolean | 模式     |
| 3    | $recursive | boolean | 是否递归 |

15、chown()

- 改变指定文件的所有者，调用示例：

```
$disk = RC_Storage::disk();
$disk->chown($file, $owner, $recursive = false);
```

| 1    | $file      | string  | 文件路径     |
| ---- | ---------- | ------- | ------------ |
| 2    | $owner     | mixed   | 用户名或数字 |
| 3    | $recursive | boolean | 是否递归     |

16、owner()

- 获取指定文件的所有者，调用示例：

```
$disk = RC_Storage::disk();
$disk->owner($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

17、group()

- 取得文件的组，调用示例：

```
$disk = RC_Storage::disk();
$disk->group($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

18、is_file()

- 判断是否是文件，调用示例：

```
$disk = RC_Storage::disk();
$disk->is_file($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

19、is_dir()

- 判断是否是目录，调用示例：

```
$disk = RC_Storage::disk();
$disk->is_dir($path);
```

| 1    | $path | string | 目录路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

20、is_readable()

- 判断是否可读，调用示例：

```
$disk = RC_Storage::disk();
$disk->is_readable($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

21、is_writable()

- 判断是否可写，调用示例：

```
$disk = RC_Storage::disk();
$disk->is_writable($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

22、atime()

- 获取指定文件的上次访问时间，调用示例：

```
$disk = RC_Storage::disk();
$disk->atime($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

23、mtime()

- 获取文件内容上次的修改时间，调用示例：

```
$disk = RC_Storage::disk();
$disk->mtime($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

24、size()

- 获取指定文件的大小，调用示例：

```
$disk = RC_Storage::disk();
$disk->size($file);
```

| 1    | $file | string | 文件路径 |
| ---- | ----- | ------ | -------- |
|      |       |        |          |

25、touch()

- 改变文件模式，调用示例：

```
$disk = RC_Storage::disk();
$disk->touch($file, $time = 0, $atime = 0)
```

| 1    | $file  | string | 文件路径     |
| ---- | ------ | ------ | ------------ |
| 2    | $time  | string | 当前时间戳   |
| 2    | $atime | string | 上次访问时间 |

26、dirlist()

- 获取目录列表，调用示例：

```
$disk = RC_Storage::disk();
$disk->dirlist($path, $include_hidden = true, $recursive = false)
```

| 1    | $path           | string  | 目录路径         |
| ---- | --------------- | ------- | ---------------- |
| 2    | $include_hidden | boolean | 是否包含隐藏文件 |
| 3    | $recursive      | boolean | 是否递归         |

27、filelist()

- 获取目录下的指定类型的文件列表，调用示例：

```
$disk = RC_Storage::disk();
$disk->filelist($path, $allowFiles, $start, $size)
```

| 1    | $path       | string | 目录路径   |
| ---- | ----------- | ------ | ---------- |
| 2    | $allowFiles | array  | 允许的文件 |
| 3    | $start      | int    | 开始位置   |
| 4    | $size       | int    | 大小       |