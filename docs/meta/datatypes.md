## Data Types 

您可以将多种不同类型的值附加到Metable模型。 Royalcms-Mediable支持的数据类型开箱即用。

## 标量值

支持以下标量值。

### Array

标量值数组。 支持嵌套数组。

```php
<?php
$metable->setMeta('information', [
        'address' => [
                'street' => '123 Somewhere Ave.',
                'city' => 'Somewhereville',
                'country' => 'Somewhereland',
                'postal' => '123456',
        ],
        'contact' => [
                'phone' => '555-555-5555',
                'email' => 'email@example.com'
        ]
]);
```

##### Warning

Royalcms-Metable在引擎盖下使用json_encode（）和json_decode（）进行数组序列化。 这将导致嵌套在数组中的任何对象都被强制转换为数组。

### Boolean

```php
<?php
$metable->setMeta('accepted_promotion', true);
```

### Integer

```php
<?php
$metable->setMeta('likes', 9001);
```

### Float

```php
<?php
$metable->setMeta('precision', 0.755);
```

### Null

```php
<?php
$metable->setMeta('linked_model', null);
```

### String

```php
<?php
$metable->setMeta('attachment', '/var/www/html/public/attachment.pdf');
```

## 对象值

支持以下类和接口。

### Eloquent Models

可以将另一个Eloquent模型附加到Metable模型。

```php
<?php
$page = App\Page::where(['title' => 'Welcome'])->first();
$metable->setMeta('linked_model', $page);
```

当调用$metable->getMeta()时，将从数据库重新加载附加的模型。

还可以附加尚未保存到数据库的Model实例。

```php
<?php
$metable->setMeta('related', new App\Page);
```

当调用$metable->getMeta()时，将创建该类的新实例（不包括任何属性）。

### Eloquent Collections

类似地，通过提供包含模型的Royalcms\Component\Database\Eloquent\Collection实例，可以将多个模型附加到键。

与单个模型一样，可以存储现有和未保存的实例。

```php
<?php
$users = App\User::where(['title' => 'developer'])->get();
$metable->setMeta('authorized', $users);
```

### DateTime & Carbon

实现DateTimeInterface的任何对象。 对象将转换为Carbon实例。

```php
<?php
$metable->setMeta('last_viewed', \Carbon\Carbon::now());
```

### Serializable

任何实现PHP Serializable接口的对象。

```php
<?php
class Example implements \Serializable
{
        //...
}

$serializable = new Example;

$metable->setMeta('example', $serializable);
```

### Plain Objects

任何其他对象都将转换为stdClass普通对象。 您可以通过在存储对象的类上实现JsonSerializable接口来控制存储的属性。

```php
<?php
$metable->setMeta('weight', new Weight(10, 'kg'));
$weight = $metable->getMeta('weight') // stdClass($amount = 10; $unit => 'kg');
```

##### 备注

Royalcms\Component\Metable\DataType\ObjectHandler类应该始终是config/metable.php数据类型数组的最后一个条目，因为它将接受任何对象，导致其下面的任何处理程序被忽略。

##### 警告

Royalcms-Metable在引擎盖下使用json_encode()和json_decode()进行普通对象序列化。 这将导致对象属性中的任何数组转换为stdClass对象。

### Adding Custom Data Types

您可以通过为类创建新的Handler来添加对其他数据类型的支持，这可以处理序列化。 只应处理可以转换为字符串然后从该字符串重建的对象。

定义一个实现Royalcms\Component\Metable\DataType\Handler接口的类，并将其注册到config/metable.php中的'datatypes'数组。 数组中处理程序的顺序很重要，因为Royalcms-Metable将遍历它们并使用第一个为给定值的canHandleValue()方法返回true的条目。 确保在更抽象的类之前有更多具体的类。