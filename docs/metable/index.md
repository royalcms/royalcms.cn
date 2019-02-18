## 介绍

Royalcms-Metable是一个可以轻松将任意数据附加到Royalcms 5的Eloquent模型的软件包。

## 功能

一对多的多态关系允许将数据附加到Eloquent模型，而无需调整数据库模式。
类型转换系统允许存储，查询和检索多种不同标量和对象类型的数据。 请参阅支持列表：[`datatypes`](datatypes)。

## 使用场景

将一些元数据附加到Eloquent的模型中

```php
<?php
$post = Post::create($this->request->input());
$post->setMeta('color', 'blue');
```

通过元数据查询模型

```php
<?php
$post = Post::whereMeta('color', 'blue');
```

从模型中检索元数据

```php
<?php
$value = $post->getMeta('color');
```

## 相关文档

- [Meta使用](handling_meta)
- [Meta查询](querying_meta)
- [Meta数据类型](datatypes)