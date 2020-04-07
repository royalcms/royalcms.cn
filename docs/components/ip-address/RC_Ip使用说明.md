### ecjia后台RC_Ip使用说明



#### 方法列表

| 编号 |  方法名称   |    简单描述    |
| :--: | :---------: | :------------: |
|  1   |   area()    | 获取ip所属地区 |
|  2   | client_ip() |  获得客户端IP  |
|  3   | server_ip() | 获取服务器的IP |

#### 方法详细说明

1、area()

- 获取当前ip所在区域，示例：

```
RC_Ip::area($ip = '', $isSimple = true, $ip_file = '');
```

| 1    | $ip       | string | ip地址           |
| ---- | --------- | ------ | ---------------- |
| 2    | $isSimple | bool   | 是否过滤具体位置 |
| 3    | $ip_file  | string | 文件名           |

2、client_ip()

- 获得客户端IP，示例：

```
RC_Ip::client_ip($type);
```

| 1    | $type | int  | 1 返回IP地址 2返回ipv4的ip数字 |
| ---- | ----- | ---- | ------------------------------ |
|      |       |      |                                |

3、server_ip()

- 获取服务器的IP，示例

```
RC_Ip::server_ip();
```