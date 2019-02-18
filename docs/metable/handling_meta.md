目录
 
- [Meta介绍](index)
- [Meta使用](handling_meta)
- [Meta查询](querying_meta)
- [Meta数据类型](datatypes)

## Meta使用

在将meta附加到Eloquent模型之前，必须先将Metable特征添加到您的Eloquent模型中。

```php
<?php

namespace App;

use Royalcms\Component\Metable\Metable;
use Royalcms\Component\Database\Eloquent\Model;

class Page extends Model
{
        use Metable;

        // ...
}
```

## 添加元数据

使用setMeta()方法将meta附加到模型。 该方法接受两个参数：用作键的字符串和值。 value参数将接受许多不同的输入，这些输入将转换为字符串以存储在数据库中。 请参阅支持的列表：`datatypes`。

```php
<?php
$model->setMeta('key', 'value');
```

要一次设置多个元键和值对，可以将关联数组或集合传递给syncMeta()。

```php
<?php
$model->syncMeta([
        'name' => 'John Doe',
        'age' => 18,
]);
```

## 检索元数据

您可以使用getMeta()方法检索给定键的元数值。 应以与存储的格式相同的格式返回该值。 例如，如果设置了数组，则在检索数组时将返回一个数组。

```php
<?php

$model->setMeta('age', 18);
$model->setMeta('approved', true);
$model->setMeta('accessed_at', Carbon::now());

//reload the model from the database
$model = $model->fresh();

$age = $model->getMeta('age'); //returns an integer
$approved = $model->getMeta('approved'); //returns a boolean
$accessDate = $model->getMeta('accessed_at'); //returns a Carbon instance

//etc.
```

您可以将第二个参数传递给方法，以指定在该键未设置元数据时返回的默认值。

```php
<?php
$model->getMeta('status', 'draft');
```

##### 备注

如果已为该键手动设置了falsey值（例如0，false，null，''），则将返回该值而不是默认值。 仅当元键值中不存在元时，才会返回默认值。

一次加载后，附加到模型实例的所有元都将缓存在模型的元关系中。 因此，对getMeta()的连续调用不会重复命中数据库。

类似地，每个元的反序列化值一旦被访问就被缓存。 这对于附加：`eloquent_models`和类似的依赖于数据库的对象特别相关。

为元键值设置新值会自动更新所有缓存。

## 检索所有元数据

要检索附加到模型的所有元的集合（表示为键和值对），请使用getAllMeta()。

```php
<?php
$meta = $model->getAllMeta();
```

## 检查元数据存在

您可以使用hasMeta()方法检查是否已将值分配给给定键。

```php
<?php
if ($model->hasMeta('background-color')) {
        // ...
}
```

##### 备注

即使已为该键手动设置了falsey值（例如0，false，null，''），此方法也将返回true。

## 删除元数据

要删除存储在给定键中的元数据，请使用removeMeta()。

```php
<?php
$model->removeMeta('prefered_language');
```

要从模型中删除所有元数据，请使用purgeMeta()。

```php
<?php
$model->purgeMeta();
```

手动删除Metable模型时，会自动从数据库中清除附加的元数据。 如果查询构建器删除了模型，则不会级联Meta。

```php
<?php
$model->delete(); // will delete attached meta
MyModel::where(...)->delete() // will NOT delete attached meta
```

## 加载元数据

使用Metable模型的集合时，请务必将所有实例的元关系一起加载，以避免重复的数据库查询（即N + 1问题）。

来自查询构建器的即时加载：

```php
<?php
$models = MyModel::with('meta')->where(...)->get();
```

来自Eloquent系列的懒人加载：

```php
<?php
$models->load('meta');
```

您还可以通过向模型的$with属性添加“meta”来指示模型类始终急切加载元关系。

```php
<?php

class MyModel extends Model {
    use Metable;

    protected $with = ['meta'];
}
```