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

Any other objects will be converted to stdClass plain objects. You can control what properties are stored by implementing the JsonSerializable interface on the class of your stored object.

```php
<?php
$metable->setMeta('weight', new Weight(10, 'kg'));
$weight = $metable->getMeta('weight') // stdClass($amount = 10; $unit => 'kg');
```

##### Note

The Royalcms\Component\Metable\DataType\ObjectHandler class should always be the last entry the config/metable.php datatypes array, as it will accept any object, causing any handlers below it to be ignored.

##### Warning

Royalcms-Metable uses json_encode() and json_decode() under the hood for plain object serialization. This will cause any arrays within the object's properties to be cast to a stdClass object.

### Adding Custom Data Types

You can add support for other data types by creating a new Handler for your class, which can take care of serialization. Only objects which can be converted to a string and then rebuilt from that string should be handled.

Define a class which implements the Royalcms\Component\Metable\DataType\Handler interface and register it to the 'datatypes' array in config/metable.php. The order of the handlers in the array is important, as Laravel-Metable will iterate through them and use the first entry that returns true for the canHandleValue() method for a given value. Make sure more concrete classes come before more abstract ones.