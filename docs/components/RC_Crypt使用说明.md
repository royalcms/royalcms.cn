### ecjia后台RC_Crypt使用说明


注：进行虚拟卡加密解密操作时，需要先更改数据表中字段长度，可查看wiki:[http://wiki.shangchina.com/index.php?title=Ecshop%E6%95%B0%E6%8D%AE%E8%A1%A8%E5%8F%98%E5%8A%A8%E8%AE%B0%E5%BD%95](http://wiki.shangchina.com/index.php?title=Ecshop数据表变动记录)

#### 目录

 [隐藏] 

- [1加密](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Crypt使用说明#.E5.8A.A0.E5.AF.86)
- [2用法例子](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Crypt使用说明#.E7.94.A8.E6.B3.95.E4.BE.8B.E5.AD.90)
- [3解密](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Crypt使用说明#.E8.A7.A3.E5.AF.86)
- [4用法例子](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Crypt使用说明#.E7.94.A8.E6.B3.95.E4.BE.8B.E5.AD.90_2)

#### 加密

旧：

```
  RC_Crypt::encrypt('加密值','auth_key值');
```

新：

```
  RC_Crypt::setKey('auth_key值');
  RC_Crypt::encrypt('加密值'); //方法中不需要第二个参数。
```

#### 用法例子

旧：

```
  $key = ecjia_config::instance()->read_config('auth_key');
  RC_Crypt::encrypt($_POST['card_sn'], $key);
```

新：

```
  $key = ecjia_config::instance()->read_config('auth_key');
  RC_Crypt::setKey($key);
  RC_Crypt::encrypt($_POST['card_sn']);
```

#### 解密

旧：

```
  RC_Crypt::decrypt('解密值','auth_key值');
```

新：

```
  RC_Crypt::decrypt('auth_key值');
  RC_Crypt::decrypt('解密值'); //方法中不需要第二个参数。
```

#### 用法例子

旧：

```
  $key = ecjia_config::instance()->read_config('auth_key');
  RC_Crypt::decrypt($_POST['card_sn'], $key);
```

新：

```
  $key = ecjia_config::instance()->read_config('auth_key');
  RC_Crypt::setKey($key);
  RC_Crypt::decrypt($_POST['card_sn']);
```