目录
 
- [Meta介绍](index)
- [Meta使用](handling_meta)
- [Meta查询](querying_meta)
- [Meta数据类型](datatypes)


## Meta查询

Metable特征提供了许多查询范围，以便于根据模型附带的元修改查询。

## 检查是否存在键值

要仅返回具有分配给特定键的值的记录，可以使用whereHasMeta()。 您还可以将数组传递给此方法，这将导致查询返回附加到一个或多个提供的键的任何模型。

```php
<?php
$models = MyModel::whereHasMeta('notes')->get();
$models = MyModel::whereHasMeta(['queued_at', 'sent_at'])->get();
```

如果您希望将查询限制为仅返回包含所有提供的键的meta的模型，则可以使用whereHasMetaKeys()。

```php
<?php
$models = MyModel::whereHasMetaKeys(['step1', 'step2', 'step3'])->get();
```

您还可以使用whereDoesntHaveMeta()查询不包含元键的记录。 它的签名与`whereHasMeta()`的签名相同。

```php
<?php
$models = MyModel::whereDoesntHaveMeta('notes')->get();
$models = MyModel::whereDoesntHaveMeta(['queued_at', 'sent_at'])->get();
```

## 比较键值

您可以根据存储在元键中的值来限制查询。 whereMeta()方法可用于使用Royalcms查询构建器的where()方法接受的任何运算符来比较值。

```php
<?php
// omit the operator (defaults to '=')
$models = MyModel::whereMeta('letters', ['a', 'b', 'c'])->get();

// greater than
$models = MyModel::whereMeta('name', '>', 'M')->get();

// like
$models = MyModel::whereMeta('summary', 'like', '%bacon%')->get();

//etc.
```

whereMetaIn()方法也可用于查找值与预定义选项集之一匹配的记录。

```php
<?php
$models = MyModel::whereMetaIn('country', ['CAN', 'USA', 'MEX']);
```

whereMeta()和whereMetaIn()方法执行字符串比较（词典排序）。 传递给这些方法的任何非字符串值都将序列化为字符串。 这对于评估等式（=）或不等式（<>）很有用，但对于非字符串数据类型可能与其他一些运算符不可预测。

```php
<?php
// array value will be serialized before it is passed to the database
$model->setMeta('letters', ['a', 'b', 'c']);

// array argument will be serialized using the same mechanism
// the original model will be found.
$model = MyModel::whereMeta('letters', ['a', 'b', 'c'])->first();
```

根据原始数据的格式，可以使用SQL like运算符和字符串参数来比较数据的子集。

```php
<?php
$model->setMeta('letters', ['a', 'b', 'c']);

// check for the presence of one value within the json encoded array
// the original model will be found
$model = MyModel::whereMeta('letters', 'like', '%"b"%' )->first();
```

将整数或浮点值与<，<=，> =或>运算符进行比较时，请使用whereMetaNumeric()方法。 这将在执行比较之前将值转换为数字，以避免词典排序的常见缺陷（例如，'11'大于'100'）。

```php
<?php
$models = MyModel::whereMetaNumeric('counter', '>', 42)->get();
```

## 结果排序

您可以将order by子句应用于查询，以按元键的值对结果进行排序。

```php
<?php
// order by string value
$models = MyModel::orderByMeta('nickname', 'asc')->get();

//order by numeric value
$models = MyModel::orderByMetaNumeric('score', 'desc')->get();
```

默认情况下，将对与查询的其余部分匹配的所有记录进行排序。 没有分配给要排序的键的元数据的任何记录将被视为具有null值。

要自动排除未分配给排序键的所有记录，请将true作为第三个参数传递。 这将在排序时执行内部联接而不是左联接。

```php
<?php
// sort by score, excluding models which have no score
$model = MyModel::orderByMetaNumeric('score', 'desc', true)->get();

//equivalent to, but more efficient than
$models = MyModel::whereHasMeta('score')
    ->orderByMetaNumeric('score', 'desc')->get();
```

## 关于优化的记录

Royalcms-Metable是处理许多不同形状和大小数据的便捷方式。 它被设计用于处理只有表中所有模型的子集才有需要的数据。

例如，您有一个带有模板字段的页面模型，每个模板都需要一些额外的字段来修改它的显示方式。 如果你有X模板，每个模板最多有Y个字段，那么将所有这些作为列添加到页面表将很快失控。 相反，将这些模板字段作为元素附加到Page模型可以使处理此用例变得微不足道。

Royalcms-Metable可以很容易地将任何数据附加到您的模型中。 但是，对于足够大的数据集或经常查询的数据，使用常规数据库列通常会更有效，以便利用本机SQL数据类型和索引。 最佳解决方案取决于您的使用案例。