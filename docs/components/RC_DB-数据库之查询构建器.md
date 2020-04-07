### RC_DB-数据库之查询构建器

#### 目录

 [隐藏] 

- [1简介](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E7.AE.80.E4.BB.8B)
- 2获取结果集
  - [2.1从一张表中取出所有行 get()](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E4.BB.8E.E4.B8.80.E5.BC.A0.E8.A1.A8.E4.B8.AD.E5.8F.96.E5.87.BA.E6.89.80.E6.9C.89.E8.A1.8C_get.28.29)
  - [2.2从一张表中获取一行/一列 first()](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E4.BB.8E.E4.B8.80.E5.BC.A0.E8.A1.A8.E4.B8.AD.E8.8E.B7.E5.8F.96.E4.B8.80.E8.A1.8C.2F.E4.B8.80.E5.88.97_first.28.29)
  - [2.3从一张表中获取组块结果集](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E4.BB.8E.E4.B8.80.E5.BC.A0.E8.A1.A8.E4.B8.AD.E8.8E.B7.E5.8F.96.E7.BB.84.E5.9D.97.E7.BB.93.E6.9E.9C.E9.9B.86)
  - [2.4获取数据列值列表](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.8E.B7.E5.8F.96.E6.95.B0.E6.8D.AE.E5.88.97.E5.80.BC.E5.88.97.E8.A1.A8)
  - [2.5聚合函数](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.81.9A.E5.90.88.E5.87.BD.E6.95.B0)
- 3查询（Select）
  - [3.1指定查询子句](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E6.8C.87.E5.AE.9A.E6.9F.A5.E8.AF.A2.E5.AD.90.E5.8F.A5)
  - [3.2原生表达式](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.8E.9F.E7.94.9F.E8.A1.A8.E8.BE.BE.E5.BC.8F)
- 4连接（Join）
  - [4.1内连接（等值连接）](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.86.85.E8.BF.9E.E6.8E.A5.EF.BC.88.E7.AD.89.E5.80.BC.E8.BF.9E.E6.8E.A5.EF.BC.89)
  - [4.2左连接](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.B7.A6.E8.BF.9E.E6.8E.A5)
  - [4.3高级连接语句](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E9.AB.98.E7.BA.A7.E8.BF.9E.E6.8E.A5.E8.AF.AD.E5.8F.A5)
- [5联合（Union）](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.81.94.E5.90.88.EF.BC.88Union.EF.BC.89)
- 6条件子句（Where）
  - [6.1简单where子句](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E7.AE.80.E5.8D.95where.E5.AD.90.E5.8F.A5)
  - [6.2or](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#or)
  - 6.3更多Where子句
    - [6.3.1whereBetween](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#whereBetween)
    - [6.3.2whereNotBetween](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#whereNotBetween)
    - [6.3.3whereIn/whereNotIn](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#whereIn.2FwhereNotIn)
    - [6.3.4whereNull/whereNotNull](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#whereNull.2FwhereNotNull)
  - 6.4高级Where子句
    - [6.4.1参数分组](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.8F.82.E6.95.B0.E5.88.86.E7.BB.84)
    - [6.4.2exists语句](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#exists.E8.AF.AD.E5.8F.A5)
- 7排序（Order by）
  - [7.1orderBy](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#orderBy)
- 8分组（Group by）
  - [8.1groupBy](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#groupBy)
  - [8.2having](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#having)
  - [8.3havingRaw](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#havingRaw)
- 9分页（Limit）
  - [9.1take](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#take)
  - [9.2skip](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#skip)
- 10插入（Insert）
  - [10.1Insert](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#Insert)
  - [10.2自增ID](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.87.AA.E5.A2.9EID)
- 11更新（Update）
  - [11.1Update](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#Update)
  - [11.2增加/减少](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.A2.9E.E5.8A.A0.2F.E5.87.8F.E5.B0.91)
- [12删除（Delete）](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.88.A0.E9.99.A4.EF.BC.88Delete.EF.BC.89)
- [13悲观锁](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E6.82.B2.E8.A7.82.E9.94.81)
- 14原生数据查询操作
  - [14.1获取数据库完整表名](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.8E.B7.E5.8F.96.E6.95.B0.E6.8D.AE.E5.BA.93.E5.AE.8C.E6.95.B4.E8.A1.A8.E5.90.8D)
  - [14.2原生数据库语句执行](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E5.8E.9F.E7.94.9F.E6.95.B0.E6.8D.AE.E5.BA.93.E8.AF.AD.E5.8F.A5.E6.89.A7.E8.A1.8C)
- 15原数据查询迁移
  - [15.1get_field](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#get_field)
  - [15.2find](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#find)
  - [15.3select](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#select)
- [16查询构造器中别名问题](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E6.9F.A5.E8.AF.A2.E6.9E.84.E9.80.A0.E5.99.A8.E4.B8.AD.E5.88.AB.E5.90.8D.E9.97.AE.E9.A2.98)
- [17更新数据中带有字段数据相加](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E6.9B.B4.E6.96.B0.E6.95.B0.E6.8D.AE.E4.B8.AD.E5.B8.A6.E6.9C.89.E5.AD.97.E6.AE.B5.E6.95.B0.E6.8D.AE.E7.9B.B8.E5.8A.A0)
- 18数据库事务
  - [18.1手动操作事务](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E6.89.8B.E5.8A.A8.E6.93.8D.E4.BD.9C.E4.BA.8B.E5.8A.A1)
- [19使用多数据库连接](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E4.BD.BF.E7.94.A8.E5.A4.9A.E6.95.B0.E6.8D.AE.E5.BA.93.E8.BF.9E.E6.8E.A5)
- [20获取查询日志](https://www.ecjia.com/wiki/ECJiaWiki:ECJia到家RC_DB-数据库之查询构建器#.E8.8E.B7.E5.8F.96.E6.9F.A5.E8.AF.A2.E6.97.A5.E5.BF.97)

#### 简介

数据库查询构建器提供了一个方便的、平滑的接口来创建和运行数据库查询。查询构建器可以用于执行应用中大部分数据库操作，并且能够在支持的所有数据库系统上工作。

```
注意：查询构建器使用PDO参数绑定来避免SQL注入攻击，不再需要过滤传递到绑定的字符串。
```

获取查询构建器很简单，还是要依赖RC_DB，我们使用RC_DB的table方法，传入表名，即可获取该表的查询构建器：

```
$users = RC_DB::table('users');
```

这样我们就获取到了$users表的查询构建器，实际上，底层返回的是Royalcms\Component\Database\Query\Builder的实例，我们对查询构建器的所有操作都是调用该实例对应类上的方法。

#### 获取结果集

##### 从一张表中取出所有行 get()

在查询之前，使用 **RC_DB** 门面的table方法，table方法为给定表返回一个查询构建器，允许你在查询上链接更多约束条件并最终返回查询结果。

使用get方法获取表中所有记录：

```
$users = RC_DB::table('users')->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users`
```

和原生查询一样，get方法返回结果集的数据组，其中每一个结果都是PHP数组。你可以像访问数组一样访问列的值：

```
foreach ($users as $user) {
    echo $user['name'];
}
```

##### 从一张表中获取一行/一列 first()

如果你只是想要从数据表中获取一行数据，可以使用first方法，该方法将会返回单个 Array 数组：

```
$user = RC_DB::table('users')->where('name', 'John')->first();
echo $user['name'];
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `name` = ?
```

##### 从一张表中获取组块结果集

如果你需要处理成千上百条数据库记录，可以考虑使用chunk方法，该方法一次获取结果集的一小块，然后填充每一小块数据到要处理的闭包，该方法在编写处理大量数据库记录命令的时候非常有用。

比如，我们可以将处理全部users表数据处理成一次处理100记录的小组块：

```
RC_DB::table('users')->chunk(100, function($users) {
    foreach ($users as $user) {
        //
    }
});
```

你可以通过从闭包函数中返回false来中止组块的运行：

```
RC_DB::table('users')->chunk(100, function($users) {
    // 处理结果集...
    return false;
});
```

##### 获取数据列值列表

如果想要获取包含单个列值的数组，可以使用lists方法，在本例中，我们获取所有title的数组：

```
$titles = RC_DB::table('roles')->lists('title');

foreach ($titles as $title) {
    echo $title;
}
```

上述查询等价于下面的SQL语句：

```
select `title` from `ecjia_roles`
```

在还可以在返回数组中为列值指定更多的自定义键（该自定义键必须是该表的其它字段列名，否则会报错）：

```
$roles = RC_DB::table('roles')->lists('title', 'name');

foreach ($roles as $name => $title) {
    echo $title;
}
```

上述查询等价于下面的SQL语句：

```
select `title`, `name` from `ecjia_roles`
```

##### 聚合函数

队列构建器还提供了很多聚合方法，比如count, max, min, avg, 和 sum，你可以在构造查询之后调用这些方法：

```
$users = RC_DB::table('users')->count();
$price = RC_DB::table('orders')->max('price');
```

上述查询等价于下面的SQL语句：

```
select max(`price`) as aggregate from `ecjia_orders`
```

当然，你可以联合其它查询字句和聚合函数来构建查询：

```
$price = RC_DB::table('orders')
                ->where('finalized', 1)
                ->avg('price');
```

上述查询等价于下面的SQL语句：

```
select avg(`price`) as aggregate from `ecjia_orders` where `finalized` = 1
```

#### 查询（Select）

##### 指定查询子句

当然，我们并不总是想要获取数据表的所有列，使用select方法，你可以为查询指定自定义的select子句：

```
$users = RC_DB::table('users')->select('name', 'email as user_email')->get();
```

上述查询等价于下面的SQL语句：

```
select `name`, `email` as `user_email` from `ecjia_users`
```

distinct方法允许你强制查询返回不重复的结果集：

```
$users = RC_DB::table('users')->distinct()->get();
```

上述查询等价于下面的SQL语句：

```
select distinct * from `ecjia_users`
```

如果你已经有了一个查询构建器实例并且希望添加一个查询列到已存在的select子句，可以使用addSelect方法：

```
$query = RC_DB::table('users')->select('name');
$users = $query->addSelect('age')->get();
```

上述查询等价于下面的SQL语句：

```
select `name`, `age` from `ecjia_users`
```

##### 原生表达式

有时候你希望在查询中使用原生表达式，这些表达式将会以字符串的形式注入到查询中，所以要格外小心避免被SQL注入。想要创建一个原生表达式，可以使用 RC_DB::raw 方法：

```
$users = RC_DB::table('users')
                     ->select(RC_DB::raw('count(*) as user_count, status'))
                     ->where('status', '<>', 1)
                     ->groupBy('status')
                     ->get();
```

上述查询等价于下面的SQL语句：

```
select count(*) as user_count, status from `ecjia_users` where `status` <> ? group by `status`
```

也可以使用selectRaw方法，等价于上述SQL语句：

```
$users = RC_DB::table('users')
                     ->selectRaw('count(*) as user_count, status')
                     ->where('status', '<>', 1)
                     ->groupBy('status')
                     ->get();
```

#### 连接（Join）

连接查询指的是将两张表或多张表关联到一起进行查询，获取一个表的行与另一个表的行匹配的数据。常见的连接查询包括内连接（等值连接）、左（外）连接、右（外）连接和交叉连接（完全连接）等。下面这张图形象的展示了这几种连接查询所获取的结果集：

[![连接查询select-join示意图.jpg](https://www.ecjia.com/wiki/images/4/41/%E8%BF%9E%E6%8E%A5%E6%9F%A5%E8%AF%A2select-join%E7%A4%BA%E6%84%8F%E5%9B%BE.jpg)](https://www.ecjia.com/wiki/文件:连接查询select-join示意图.jpg)

##### 内连接（等值连接）

查询构建器还可以用于编写基本的SQL“内连接”，你可以使用查询构建器实例上的join方法，传递给join方法的第一次参数是你需要连接到的表名，剩余的其它参数则是为连接指定的列约束，当然，正如你所看到的，你可以在单个查询中连接多张表：

```
$users = RC_DB::table('users')
            ->join('contacts', 'users.id', '=', 'contacts.user_id')
            ->join('orders', 'users.id', '=', 'orders.user_id')
            ->select('users.*', 'contacts.phone', 'orders.price')
            ->get();
```

上述查询等价于下面的SQL语句：

```
select `ecjia_users`.*, `ecjia_contacts`.`phone`, `ecjia_orders`.`price` 
from `ecjia_users` inner join `ecjia_contacts` on `ecjia_users`.`id` = `ecjia_contacts`.`user_id` 
inner join `ecjia_orders` on `ecjia_users`.`id` = `ecjia_orders`.`user_id`
```

##### 左连接

如果你是想要执行“左连接”而不是“内连接”，可以使用leftJoin方法。该方法和join方法的使用方法一样：

```
$users = RC_DB::table('users')
            ->leftJoin('posts', 'users.id', '=', 'posts.user_id')
            ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` left join `ecjia_posts` on `ecjia_users`.`id` = `ecjia_posts`.`user_id`
```

##### 高级连接语句

你还可以指定更多的高级连接子句，传递一个闭包到join方法作为该方法的第2个参数，该闭包将会返回允许你指定join子句约束的JoinClause对象：

```
RC_DB::table('users')
        ->join('contacts', function ($join) {
            $join->on('users.id', '=', 'contacts.user_id')->orOn(...);
        })
        ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` inner join `ecjia_contacts` on `ecjia_users`.`id` = `ecjia_contacts`.`user_id` or `ecjia_users`.`aid` = `ecjia_contacts`.`aid`
```

如果你想要在连接中使用“where”风格的子句，可以在查询中使用where和orWhere方法。这些方法将会将列和值进行比较而不是列和列进行比较：

```
RC_DB::table('users')
        ->join('contacts', function ($join) {
            $join->on('users.id', '=', 'contacts.user_id')
                 ->where('contacts.user_id', '>', 5);
        })
        ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` inner join `ecjia_contacts` on `ecjia_users`.`id` = `ecjia_contacts`.`user_id` and `ecjia_contacts`.`user_id` > ?
```

#### 联合（Union）

查询构建器还提供了一条“联合”两个查询的快捷方式，比如，你要创建一个独立的查询，然后使用union方法将其和第二个查询进行联合：

```
$first = RC_DB::table('users')
            ->whereNull('first_name');

$users = RC_DB::table('users')
            ->whereNull('last_name')
            ->union($first)
            ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `first_name` is null

(select * from `ecjia_users` where `last_name` is null) union (select * from `ecjia_users` where `first_name` is null)
```

unionAll方法也是有效的，并且和union有同样的使用方法。

#### 条件子句（Where）

##### 简单where子句

使用查询构建器上的where方法可以添加where子句到查询中，调用where最基本的方法需要三个参数，第一个参数是列名，第二个参数是一个数据库系统支持的任意操作符，第三个参数是该列要比较的值。

例如，下面是一个验证“votes”列的值是否等于100的查询：

```
$users = RC_DB::table('users')->where('votes', '=', 100)->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` = ?
```

为了方便，如果你只是简单比较列值和给定数值是否相等，可以将数值直接作为where方法的第二个参数：

```
$users = RC_DB::table('users')->where('votes', 100)->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` = ?
```

当然，你可以使用其它操作符来编写where子句：

```
$users = RC_DB::table('users')
                ->where('votes', '>=', 100)
                ->get();

$users = RC_DB::table('users')
                ->where('votes', '<>', 100)
                ->get();

$users = RC_DB::table('users')
                ->where('name', 'like', 'T%')
                ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` >= ?

select * from `ecjia_users` where `votes` <> ?

select * from `ecjia_users` where `name` like ?
```

##### or

你可以通过方法链将多个where约束链接到一起，也可以添加or子句到查询，orWhere方法和where方法接收参数一样：

```
$users = RC_DB::table('users')
                    ->where('votes', '>', 100)
                    ->orWhere('name', 'John')
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` > ? or `name` = ?
```

##### 更多Where子句

###### whereBetween

whereBetween方法验证列值是否在给定值之间：

```
$users = RC_DB::table('users')
                    ->whereBetween('votes', [1, 100])->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` between ? and ?
```

###### whereNotBetween

whereNotBetween方法验证列值不在给定值之间：

```
$users = RC_DB::table('users')
                    ->whereNotBetween('votes', [1, 100])
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` not between ? and ?
```

###### whereIn/whereNotIn

whereIn方法验证给定列的值是否在给定数组中：

```
$users = RC_DB::table('users')
                    ->whereIn('id', [1, 2, 3])
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `id` in (?, ?, ?)
```

whereNotIn方法验证给定列的值不在给定数组中：

```
$users = RC_DB::table('users')
                    ->whereNotIn('id', [1, 2, 3])
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `id` not in (?, ?, ?)
```

###### whereNull/whereNotNull

whereNull方法验证给定列的值为NULL：

```
$users = RC_DB::table('users')
                    ->whereNull('updated_at')
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `updated_at` is null
```

whereNotNull方法验证给定列的值不是NULL：

```
$users = RC_DB::table('users')
                    ->whereNotNull('updated_at')
                    ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `updated_at` is not null
```

##### 高级Where子句

###### 参数分组

有时候你需要创建更加高级的where子句比如”where exists“或者嵌套的参数分组。查询构建器也可以处理这些。

作为开始，让我们看一个在括号中进行分组约束的例子：

```
RC_DB::table('users')
            ->where('name', '=', 'John')
            ->orWhere(function ($query) {
                $query->where('votes', '>', 100)
                      ->where('title', '<>', 'Admin');
            })
            ->get();
```

正如你所看到的，传递闭包到orWhere方法构造查询构建器来开始一个约束分组，该闭包将会获取一个用于设置括号中包含的约束的查询构建器实例。上述语句等价于下面的SQL：

```
select * from users where name = 'John' or (votes > 100 and title <> 'Admin')
```

当传入变量时，使用方法如下面的例子：

```
$keywords = 'test';
RC_DB::table('users')
            ->where('name', '=', 'John')
            ->orWhere(function($query) use ($keywords) {
                $query->where('votes', '>', 100)
                      ->where('title', '<>', 'Admin')
                      ->where('keywords', 'like', '%'.mysql_like_quote($keywords).'%');
            })
            ->get();
```

上述语句等价于

```
select * from users where name = 'John' or (votes > 100 and title <> 'Admin' and keywords like '%test%')
```

###### exists语句

whereExists方法允许你编写where existSQL子句，whereExists方法接收一个闭包参数，该闭包获取一个查询构建器实例从而允许你定义放置在”exists”子句中的查询：

```
RC_DB::table('users')
            ->whereExists(function ($query) {
                $query->select(DB::raw(1))
                      ->from('orders')
                      ->whereRaw('orders.user_id = users.id');
            })
            ->get();
```

上述查询等价于下面的SQL语句：

```
select * from users
where exists (
    select 1 from orders where orders.user_id = users.id
)
```

#### 排序（Order by）

##### orderBy

orderBy方法允许你通过给定列对结果集进行排序，orderBy的第一个参数应该是你希望排序的列，第二个参数控制着排序的方向——asc或desc： 根据代码可以看到orderBy方法需要传入两个参数，第一个是排序字段，第二个是排序方向，asc代表升序，desc代表倒序。

升序：

```
$users = RC_DB::table('users')
                ->orderBy('name', 'asc')
                ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` order by `name` asc
```

降序：

```
$users = RC_DB::table('users')
                ->orderBy('name', 'desc')
                ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` order by `name` desc
```

#### 分组（Group by）

分组一般用于聚合查询。

##### groupBy

groupBy方法用于对结果集进行分组：

```
$users = RC_DB::table('users')
                ->groupBy('account_id')
                ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` group by `account_id`
```

##### having

groupBy和having方法用于对结果集进行分组，having方法和where方法的用法类似：

```
$users = RC_DB::table('users')
                ->groupBy('account_id')
                ->having('account_id', '>', 100)
                ->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` group by `account_id` having `account_id` > ?
```

##### havingRaw

havingRaw方法可以用于设置原生字符串作为having子句的值，例如，我们要找到所有售价大于$2500的部分：

```
$users = RC_DB::table('orders')
                ->select('department', DB::raw('SUM(price) as total_sales'))
                ->groupBy('department')
                ->havingRaw('SUM(price) > 2500')
                ->get();
```

上述查询等价于下面的SQL语句：

```
select `department`, SUM(price) as total_sales from `ecjia_orders` group by `department` having SUM(price) > 2500
注意：having中的条件字段必须出现在select查询字段中，否则会报错。
```

#### 分页（Limit）

查询构建器中使用skip和take对查询结果进行分页，相当于SQL语句中的limit语句：

##### take

想要限定查询返回的结果集的数目，可以使用take方法：

```
$users = RC_DB::table('users')->take(5)->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` limit 5
```

##### skip

想要限定查询返回的结果集的数目，或者在查询中跳过给定数目的结果，可以使用skip和take方法：

```
$users = RC_DB::table('users')->skip(10)->get();

$users = RC_DB::table('users')->skip(10)->take(5)->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` offset 10

select * from `ecjia_users` limit 5 offset 10
```

#### 插入（Insert）

##### Insert

查询构建器还提供了insert方法来插入记录到数据表。insert方法接收数组形式的列名和值进行插入操作：

```
RC_DB::table('users')->insert(
    ['email' => 'john@example.com', 'votes' => 0]);
```

上述查询等价于下面的SQL语句：

```
insert into `ecjia_users` (`email`, `votes`) values (john@example.com, 0)
```

你甚至可以一次性通过传入多个数组来插入多条记录，每个数组代表要插入数据表的记录（原batch_insert）：

```
RC_DB::table('users')->insert([
    ['email' => 'taylor@example.com', 'votes' => 0],
    ['email' => 'dayle@example.com', 'votes' => 0]
]);
```

上述查询等价于下面的SQL语句：

```
insert into `ecjia_users` (`email`, `votes`) values (taylor@example.com, 0), (dayle@example.com, 0)
```

##### 自增ID

如果数据表有自增ID，使用insertGetId方法来插入记录将会返回ID值：

```
$insertId = RC_DB::table('users')->insertGetId(
    ['email' => 'john@example.com', 'votes' => 0]
);
```

上述查询等价于下面的SQL语句：

```
insert into `ecjia_users` (`email`, `votes`) values (john@example.com, 0)
注意：当使用PostgresSQL时insertGetId方法默认自增列被命名为id，如果你想要从其他”序列“获取ID，可以将序列名作为第二个参数传递到insertGetId方法。
```

#### 更新（Update）

##### Update

当然，除了插入记录到数据库，查询构建器还可以通过使用update方法更新已有记录。

update方法和insert方法一样，接收列和值的键值对数组包含要更新的列，你可以通过where子句来对update查询进行约束：

```
$affected = RC_DB::table('users')
            ->where('id', 1)
            ->update(['votes' => 1]);
```

上述查询等价于下面的SQL语句：

```
update `ecjia_users` set `votes` = 1 where `id` = 1
```

该方法返回受影响的函数。

##### 增加/减少

查询构建器还提供了方便增减给定列名数值的方法。相较于编写update语句，这是一条捷径，提供了更好的体验和测试接口。

这两个方法都至少接收一个参数：需要修改的列。第二个参数是可选的，用于控制列值增加/减少的数目。

增加：

```
RC_DB::table('users')->increment('votes');
RC_DB::table('users')->increment('votes', 5);
```

上述查询等价于下面的SQL语句：

```
update `ecjia_users` set `votes` = `votes` + 1
update `ecjia_users` set `votes` = `votes` + 5
```

减少：

```
RC_DB::table('users')->decrement('votes');
RC_DB::table('users')->decrement('votes', 5);
```

上述查询等价于下面的SQL语句：

```
update `ecjia_users` set `votes` = `votes` - 1
update `ecjia_users` set `votes` = `votes` - 5
```

在操作过程中你还可以指定额外的列进行更新：

```
RC_DB::table('users')->increment('votes', 1, ['name' => 'John']);
```

上述查询等价于下面的SQL语句：

```
update `ecjia_users` set `votes` = `votes` + 1, `name` = John
```

#### 删除（Delete）

当然，查询构建器还可以通过delete方法从表中删除记录：

```
RC_DB::table('users')->delete();
```

上述查询等价于下面的SQL语句：

```
delete from `ecjia_users`
```

在调用delete方法之前可以通过添加where子句对delete语句进行约束：

```
RC_DB::table('users')->where('votes', '<', 100)->delete();
```

上述查询等价于下面的SQL语句：

```
delete from `ecjia_users` where `votes` < 100
```

使用delete方法删除表记录，删除方法和更新方法类似，返回被删除的行数：

```
$deleted = RC_DB::table('users')->where('id', '>', 3)->delete();
```

上述查询等价于下面的SQL语句：

```
delete from `ecjia_users` where `id` > 3
```

如果你希望清除整张表，也就是删除所有列并将自增ID置为0，可以使用truncate方法：

```
RC_DB::table('users')->truncate();
```

#### 悲观锁

查询构建器还包含一些方法帮助你在select语句中实现”悲观锁“。

可以在查询中使用sharedLock方法从而在运行语句时带一把”共享锁“。

共享锁可以避免被选择的行被修改直到事务提交：

```
RC_DB::table('users')->where('votes', '>', 100)->sharedLock()->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` > ? lock in share mode
```

此外你还可以使用lockForUpdate方法。”for update“锁避免选择行被其它共享锁修改或删除：

```
RC_DB::table('users')->where('votes', '>', 100)->lockForUpdate()->get();
```

上述查询等价于下面的SQL语句：

```
select * from `ecjia_users` where `votes` > ? for update
```

#### 原生数据查询操作

##### 获取数据库完整表名

获取的是带有表前缀的数据库名

```
$table = RC_DB::getTableFullName('user');
```

##### 原生数据库语句执行

```
RC_DB::statement("ALTER TABLE `$table` MODIFY `connect_code` VARCHAR(30);");
```

#### 原数据查询迁移

##### get_field

get_field($field, $return_all = false) 方法获取某个值：

替换成 pluck 方法

```
$parent_id = RC_DB::table('shop_config')->where('code', 'basic')->where('parent_id', 0)->pluck('id');
```

get_field($field, $return_all = false) 方法获取查询结果，第二个参数为true时：

替换成 lists 方法

```
$parent_id = RC_DB::table('goods')->lists('goods_id');
```

##### find

find() 查询一条记录：

替换成first方法

```
$user_info = RC_DB::table('users')->where('user_id', $user_id)->first();
```

##### select

select() 查找满足条件的所有记录：

替换成get方法

```
$user_list = RC_DB::table('users')->where('user_id', $user_id)->get();
```

#### 查询构造器中别名问题

```
RC_DB::table('adviser_log AS al')
    		->leftJoin('mobile_device', 'mobile_device.id', '=', RC_DB::raw('al.device_id'))
    		->leftJoin('adviser', 'adviser.id', '=', RC_DB::raw('al.adviser_id'))
    		->leftJoin('order_info AS oi', RC_DB::raw('oi.order_id'), '=', RC_DB::raw('al.order_id'))
    		->select(RC_DB::raw('oi.order_id, oi.order_sn, al.device_id, al.device_id, al.adviser_id'), 
                  'mobile_device.device_name', 'adviser.username',
                  RC_DB::raw('sum(oi.goods_amount + oi.tax + oi.shipping_fee + oi.insure_fee + oi.pay_fee + oi.pack_fee + oi.card_fee) as order_total_fee'),
    		  RC_DB::raw('count(al.order_id) AS order_count'))
    		->groupby(RC_DB::raw('al.device_id'), RC_DB::raw('al.adviser_id'))
    		->get();
```

上述查询等价于下面的SQL语句：

```
select oi.order_id, oi.order_sn, al.device_id, al.device_id, al.adviser_id, `ecjia_mobile_device`.`device_name`, `ecjia_adviser`.`username`, 
sum(oi.goods_amount + oi.tax + oi.shipping_fee + oi.insure_fee + oi.pay_fee + oi.pack_fee + oi.card_fee) as order_total_fee, 
count(al.order_id) AS order_count from `ecjia_adviser_log` as `al` 
left join `ecjia_mobile_device` on `ecjia_mobile_device`.`id` = al.device_id 
left join `ecjia_adviser` on `ecjia_adviser`.`id` = al.adviser_id 
left join `ecjia_order_info` as `oi` on oi.order_id = al.order_id 
group by al.device_id, al.adviser_id
```

总结：给表起别名，直接写就可以；但在select语句中要用到表的别名来得到字段，我们就要在外面套一层RC_DB::raw()。

#### 更新数据中带有字段数据相加

```
RC_DB::table('store_franchisee')->where('confirm_time', '>', 0)->where('expired_time', '=', 0)->update(['expired_time' => RC_DB::raw('`confirm_time` + 31536000')]);
```

上述查询等价于下面的SQL语句：

```
UPDATE `ecjia_store_franchisee` SET `expired_time` = `confirm_time` + 31536000 WHERE `confirm_time` > 0 AND `expired_time` = 0;
```

#### 数据库事务

要想在数据库事务中运行一组操作，则可以在 `RC_DB` facade 中使用 `transaction` 方法。如果在事务的`闭包`内抛出异常，事务将会被自动还原。如果`闭包`运行成功，事务将被自动提交。你不需要担心在使用 `transaction` 方法时还需要亲自去手动还原或提交事务：

```
    RC_DB::transaction(function () {
        RC_DB::table('users')->update(['votes' => 1]);

        RC_DB::table('posts')->delete();
    });
```

###### 手动操作事务

如果你想手动处理事务并对还原或提交操作进行完全控制，则可以在 `RC_DB` facade 使用 `beginTransaction` 方法：

```
    RC_DB::beginTransaction();
```

你也可以通过 `rollBack` 方法来还原事务：

```
    RC_DB::rollBack();
```

最后，可以通过 `commit` 方法来提交这个事务：

```
    RC_DB::commit();
```

\> **注意：** `RC_DB` facade 的事务方法也可以用来控制 [查询语句构造器] 及 [Eloquent ORM] 的事务。

#### 使用多数据库连接

当你使用了多个连接时，则可以通过 `RC_DB` facade 的 `connection` 方法来访问每个连接。传递给 `connection` 方法的 `name` 必须对应至 `config/database.php` 配置文件中的连接列表的其中一个：

```
   $users = RC_DB::connection('foo')->select(...);
```

你也可以在连接的实例中使用 `getPdo` 方法访问原始的底层 PDO 实例：

```
   $pdo = RC_DB::connection()->getPdo();
```

#### 获取查询日志

开启查询日志

```
   RC_DB::enableQueryLog();
```

获取查询日志

```
   RC_DB::getQueryLog()
```