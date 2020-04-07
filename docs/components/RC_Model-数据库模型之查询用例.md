

## ECJia到家RC_Model-数据库模型之查询用例

### 基于 ECJia数据模型 构建的 Sql UnitTest 数据库单元测试用例

### 1、test_find（单条查询返回的是一维数据）

单条查找返回的是一维数据，返回第一条记录
SELECT * FROM `ecs_admin_log` LIMIT 1

```php
$this->db_vote->find();
```

### 2、test_find（查询主键为 10 的记录）

查询主键为 10 的记录
SELECT * FROM `ecs_admin_log` WHERE `log_id`=10 LIMIT 1

```php
$this->db_admin_log->find(10);
```

### 3、test_select （查询表中的所有记录）

SELECT * FROM `ecs_admin_log`

```php
$this->db_admin_log->select();
```

### 4、test_where_order_find（查询单条记录，支持条件和排序）

SELECT * FROM `ecs_admin_log` WHERE `log_id`>2 ORDER BY `log_id` LIMIT 1

```php
$this->db_admin_log->where('`log_id`>2')->order('`log_id`')->find();
```

### 5、test_where_group_having_limit_select（查询所有记录，支持条件、分组、having、数量）

SELECT * FROM `ecs_admin_log` WHERE `log_id`>2 GROUP BY `user_id` HAVING `log_id`>2 LIMIT 3

```php
$this->db_admin_log->where('`log_id`>2')->group('user_id')->having('`log_id`>2')->limit(3)->select();
```

#### 6、test_field_find（指定字段，指定条件查询单条记录）

查找 age 字段大于 22 的记录条数
SELECT count(`log_id`) as logcount FROM `ecs_admin_log` WHERE user_id=1 LIMIT 1

```php
$this->db_admin_log->field('count(`log_id`) as logcount')->find('user_id=1');
```

### 7、test_where_select（以 ORM 方式进行组合查询多条数据）

以 ORM 方式进行组合查询
SELECT * FROM `ecs_admin_log` WHERE `user_id` = 1 AND `ip_address` = '127.0.0.1'

```php
$this->db_admin_log->where = '`user_id` = 1';
$this->db_admin_log->where = "`ip_address` = '127.0.0.1'";
$this->db_admin_log->select();
```
### 8、test_table_select（快速切换操作表）

通过 table() 方法可快速切换操作表
SELECT * FROM `ecs_vote` WHERE `start_time` > 20

```php
$this->db_admin_log->table('vote')->select('`start_time` > 20');
```

#### 9、test_table_select（ORM：快速切换操作表 ）

通过 ORM 方式设置，通过 table() 方法可快速切换操作表
SELECT * FROM `ecs_vote` WHERE `end_time` > 20

```php
$this->db_admin_log->table = 'vote';
$this->db_admin_log->select('`end_time` > 20');
```

### 10、test_version（获取数据库版本号）

5.5.33

```php
$this->db_admin_log->version();
```

### 11、test_cache_select（获取数据，支持缓存）

以下方式 SQL 不会被缓存
cache() 的参数为 0 时，不缓存
SELECT * FROM `ecs_admin_log`

```php
$this->db_admin_log->cache()->select();
```

### 12、test_cache_limit_select（获取数据，使用缓存）

以下查询结果会缓存 30 秒
SELECT * FROM `ecs_admin_log` LIMIT 20

```php
$this->db_admin_log->cache(30)->limit(20)->select();
```

### 13、test_cache_limit_select（ORM：获取数据，使用缓存）

SELECT * FROM `ecs_admin_log` LIMIT 10

```php
$this->db_admin_log->cache = 200;
$this->db_admin_log->limit = 10;
$this->db_admin_log->select();
```

### 14、test_order_max(获取表中最大值的id值)

获得最大值,与 SQL 中的 MAX 意思相同
求表 admin_log 中的最大 log_id 字段
SELECT MAX(`log_id`) AS `maxlogid` FROM `ecs_admin_log` ORDER BY `log_id` ASC

```php
$this->db_admin_log->order('`log_id` ASC')->max('`log_id`|`maxlogid`');
```

### 15、test_where_max(获取表中含有某会员名字的最大id值的记录)

统计 log_info 字段含有 会员 的最大的记录
SELECT MAX(log_id) AS log_id FROM `ecs_admin_log` WHERE `log_info` like "%会员%"

```php
$this->db_admin_log->where('`log_info` like "%会员%"')->max();
```

### 16、test_min(获取表中最小id值的记录)

获得最小值,与 SQL 中的 MIN 意思相同
求表 user 中 uid 字段最小的记录
SELECT MIN(`log_id`) FROM `ecs_admin_log`

```php
$this->db_admin_log->min('`log_id`');
```

### 17、test_min(获取表中最小记录的id并起别名)

通过 | 指定别名,以上代码求 admin_log 表中的最小 log_id 字段,并且另起别名 logidmin
SELECT MIN(`log_id`) AS `logidmin` FROM `ecs_admin_log`

```php
$this->db_admin_log->min('`log_id`|`logidmin`');
```

### 18、test_where_min(获取表中以某会员名开头的最小记录并其别名)

在 user 表中求 admin_log 以李开头的, log_id 值为最小的记录,同时通过 | 线符号为 log_id 字段起别名为 logidmin
SELECT MIN(`log_id`) AS `logidmin` FROM `ecs_admin_log` WHERE `log_info` like "安装%"

```php
$this->db_admin_log->where('`log_info` like "安装%"')->min('`log_id`|`logidmin`');
```

### 19、test_avg(获取表中某字段的平均值并给字段起别名)

获得平均值与 SQL 中的 AVG 意思相同
SELECT AVG(`log_id`) AS `logidavg` FROM `ecs_admin_log`

```php
$this->db_admin_log->avg('`log_id`|`logidavg`');
```

### 20、test_sum(获取表中某字段的总和并给该字段起别名)

通过 | 指定别名,以上代码求 admin_log 表中的 log_id 总和,并且另起别名 total
SELECT SUM(`log_id`) AS `total` FROM `ecs_admin_log`

```php
$this->db_admin_log->sum('`log_id`|`total`');
```

### 21、test_count(获取表中所有记录的记录数)

对 admin_log 表中的所有记录进行统计,返回值为数字
SELECT COUNT(log_id) AS log_id FROM `ecs_admin_log`

```php
$this->db_admin_log->count();
```

### 22、test_where_count(获取表中某个字段有相同值的记录数)

对 admin_log 表中 log_info 字段包含 编辑 的进行统计
SELECT COUNT(log_id) AS log_id FROM `ecs_admin_log` WHERE `log_info` like "%编辑%"

```php
$this->db_admin_log->where('`log_info` like "%编辑%"')->count();
```

### 23、test_where(获取表中指定字段查找的记录数)

在 admin_log 表中统计 log_id 记录数量
SELECT COUNT(`log_id`) FROM `ecs_admin_log`

```php
$this->db_admin_log->count('`log_id`');
```

### 24、test_where_group_count(获取表中满足条件的所有记录，支持分组)

SELECT COUNT(`user_id`) AS `cc` FROM `ecs_admin_log` WHERE `log_id`>10 GROUP BY `user_id`

```php
$this->db_admin_log->where('`log_id`>10')->group('user_id')->count('`user_id`|`cc`');
```

### 25、test_field_select(查询表中多个字段的值的数据集并给字段起别名)

查询表 admin_log,返回 log_id、user_id 字段数据集
SELECT `log_id`,`user_id` AS `uid` FROM `ecs_admin_log`

```php
$this->db_admin_log->field('`log_id`, `user_id`|`uid`')->select();
```

### 26、test_field_select(查询表中多个字段的值的数据集)

查询表 admin_log,返回 log_id、user_id 字段数据集
SELECT `log_id`,`user_id` FROM `ecs_admin_log`

```php
$this->db_admin_log->field(array('`log_id`', '`user_id`'))->select();
```

### 27、test_limit_order_select(查询表中前两条记录，支持排序)

limit 方法就是为了生成 SQL 的 limit 部分
以 log_time 进行降序排列, 取得前 2 个记录
SELECT * FROM `ecs_admin_log` ORDER BY `log_time` DESC LIMIT 2

```php
$this->db_admin_log->limit(2)->order('`log_time` DESC')->select();
```

### 28、test_limit_select(查询表中指定开始位置的两条记录)

指定 2 个参数来生成 limit
SELECT * FROM `ecs_admin_log` LIMIT 1,2

```php
$this->db_admin_log->limit(array(1,2))->select();
```

### 29、属性映射方式

以对象属性的方式生成 limit 部分
SELECT * FROM `ecs_admin_log` LIMIT 10,6

```php
$this->db_admin_log->limit(10,6);
$this->db_admin_log->select();
```

### 30、test_in(查询表中主键在某个数组集的的记录)

in 关联字与原生 SQL 中的 in 意思是一样的,用于匹配 in 表达式中的多个值
多参数传递
查找 admin_log 表中主键为 1 或 2 的记录集
SELECT * FROM `ecs_admin_log` WHERE log_id IN(1,2)

```php
$this->db_admin_log->in('1,2')->select();
```

### 31、test_in(查询表中主键在某个数组集的的记录，支持数组传参)

以数组形式传递参数
查找 admin_log 表中主键为 3 或 4 的记录集
SELECT * FROM `ecs_admin_log` WHERE log_id IN(3,4)

```php
$this->db_admin_log->in(array(3,4))->select();
```

### 32、test_in(查询表中指定字段在某个数组集的的记录，支持数组传参)

查找 admin_log 表中指定字段为 1 或 2 的记录集
SELECT * FROM `ecs_admin_log` WHERE user_id IN(1,2)

```php
$this->db_admin_log->in(array('user_id' => array(1,2)))->select();
```

### 33、test_field_in_find(查找某个字段的值为指定值的记录)

查找 username 字段为 ecshop 或 text 的值
SELECT user_name,user_id FROM `ecs_users` WHERE user_name IN('ecshop','text') LIMIT 1

```php
$this->db_users->field('user_name,user_id')->in(array('user_name'=>array('ecshop','text')))->find();
```

### 34、test_where_find(查找表中多个where条件的记录)

通过 where 方法操作 SQL 条件,可以指定多种参数类型,非常自由
参数为字符串
SELECT * FROM `ecs_users` WHERE user_id = 1 or user_name = 'ecshop' LIMIT 1

```php
$this->db_users->where("user_id = 1 or user_name = 'ecshop'")->find();
```

### 35、test_where_find(查找表中多个where条件的记录，以数组形式查找)

查找 user_id=2 的数据
SELECT * FROM `ecs_users` WHERE user_id=2 LIMIT 1

```php
$this->db_users->where(array('user_id' => 2))->find();
```

### 36、test_where_find(查询表中某个字段等于多个值的记录，以数组形式传参)

查找 user_id 属于 1、2、3 的数据
SELECT * FROM `ecs_users` WHERE user_id IN(1,2,3)

```php
$this->db_users->where(array('user_id' => array(1, 2, 3)))->select();
```

### 37、test_where_find(查找表中某字段在某个范围内的记录，以数组形式传参)

查找 user_id 小于等于 8 并且大于 2 的数据
SELECT * FROM `ecs_users` WHERE user_id <= 8 AND user_id > 2 LIMIT 1

```php
$this->db_users->where(array('user_id' => array('elt' => 8, 'gt' => 2)))->find();
```

### 38、test_where_find(查找表中几个字段都符合条件的记录，以数组形式传参)

查找 user_id 不等于 22 或者 user_name 等于 'ecshop' 的数据
SELECT * FROM `ecs_users` WHERE user_id <> 22 OR user_name = 'ecshop' LIMIT 1

```php
$this->db_users->where(array('user_id' => array('neq' => 22), 'or', 'user_name' => array('eq' => 'ecshop')))->find();
```

### 39、test_where->select(通过属性查询满足特定条件的记录)

可以直接使用类似 ORM 方式完成查询操作,以上所有 where 的参数均可 以通过以对象属性方式指定,非常简便
SELECT * FROM `ecs_users` WHERE user_id IN(1,22,3)

```php
$this->db_users->where = array('user_id' => array('neq' => 2), 'user_id' => array(1, 22, 3));
$this->db_users->select();
```

### 40、test_order_select(查询表中以某个字段排序的数据集)

生成 SQL 语句中的排序 ORDER BY 部分
查询所有记录以 user_id 降序
SELECT * FROM `ecs_users` ORDER BY user_id DESC

```php
$this->db_users->order('user_id DESC')->select();
```

### 41、test_order_select(查询表中以数组形式指定参数进行排序的数据集)

以数组形式指定参数进行排序
SELECT * FROM `ecs_users` ORDER BY user_id ASC

```php
$this->db_users->order(array('user_id' => 'ASC'))->select();
```

### 42、test_order_select(查询表中满足多个字段排序的数据集，以数组形式传参)

传递数组与字符串两种参数类型,指定排序规则
SELECT * FROM `ecs_users` ORDER BY user_id ASC, user_name DESC

```php
$this->db_users->order(array('user_id' => 'ASC', 'user_name' => 'DESC'))->select();
```

### 43、test_where_get_field(获取表中以指定的字段名查询的数据集)

为了使查询更加灵活, 提供了 get_field 按字段名获得结果的方法
无论结果有多少个只返回一个值
SELECT user_name FROM `ecs_users` WHERE user_id=3

```php
$this->db_users->where('user_id=3')->get_field('user_name');
```

### 44、test_where_get_field(获取表中以指定的字段名查询的数据集，并将结果存入一个数组)

返回满足条件的记录 , 并压入一个数组中
SELECT user_name FROM `ecs_users` WHERE user_id>2

```php
$this->db_users->where('user_id>2')->get_field('user_name', true);
```

### 45、test_get_field(获取表中多个字段关联查询的数据集，以第一个字段作为键名)

多个字段返回关联数组,第一个字段做为键名使用
SELECT user_id,user_name,email FROM `ecs_users`

```php
$this->db_users->get_field('user_id, user_name, email');
```

### 46、test_group_select(查询表中以某个特定字段分组的数据集)

提供了完善的分组操作方法,自由指定分组参数使发送 SQL 更容易
以 user_name 字段分组查询
SELECT * FROM `ecs_users` GROUP BY user_name

```php
$this->db_users->group('user_name')->select();
```

### 47、test_group_select(查询表中以多个字段分组查询的数据集)

以字段 user_id、user_name 进行分组查询
SELECT * FROM `ecs_users` GROUP BY user_id, user_name

```php
$this->db_users->group('user_id, user_name')->select();
```

### 48、test_group_select(查询表中以多个字段分组查询的数据集，以数组作为参数)

以字段 user_id、user_name 进行分组查询
SELECT * FROM `ecs_users` GROUP BY user_id, user_name

```php
$this->db_users->group(array('user_id', 'user_name'))->select();
```

### 49、test_group_field_select(查询表中以多个字段分组查询的数据集，属性映射)

以对象属性来指定分组参数,参数与方法 group() 传递的一样即可
SELECT user_name FROM `ecs_users` GROUP BY user_id,email

```php
$this->db_users->group = array('user_id', 'email');
$this->db_users->field = array('user_name', 'email');
$this->db_users->select();
```

### 50、test_having_group_select(查询表中满足指定字段分组并支持having查询的数据集)

在 SQL 中增加 HAVING 子句原因是,WHERE 关键字无法与合计函数一起使用 , 所以 使用 HAVING 对分组进行条件筛选 , 所以在使用 HAVING 时应该使用 group 分组。
以字段 user_name 进行分组,查询 user_id 大于 2 及 rank_points 小于 20 的数据
SELECT * FROM `ecs_users` GROUP BY user_name HAVING user_id > 2 and rank_points < 20

```php
$this->db_users->having('user_id > 2 and rank_points < 20')->group('user_name')->select();
```

### 51、test_having_group_select(查询表中满足指定字段分组并支持having查询的数据集,属性映射)

SELECT * FROM `ecs_users` GROUP BY user_name HAVING user_id > 2 and user_name like "test%"

```php
$this->db_users->having = 'user_id > 2 and user_name like "test%"';
$this->db_users->group = 'user_name';
$this->db_users->select();
```

### 52、test_post_insert(以 post形式传参想表中增加记录)

提供了非常便捷的插入操作,具有以下几个特点
a. 自动过滤非法字段
b. 自动对插入数据进行安全处理
c. 没有传入参数,则系统会自动将 $_POST 数据插入
如果无参数默认以 $_POST 为数据源
返回成功插入记录的 ID 值
INSERT INTO ecs_users(`user_name`,`password`,`email`)VALUES ("test202","e10adc3949ba59abbe56e057f20f883e","test202@163.com")

```php
$_POST = array(
	'user_name' => 'test202',
	'password' => md5(123456),
	'email' => 'test202@163.com'
);
$this->db_users->insert();
```

### 53、test_post_insert(以 post形式传参想表中增加记录，并返回插入的id值)

插入成功后, 会返回最后插入的主键 ID 值
INSERT INTO ecs_users(`user_name`,`password`,`email`)VALUES ("test203","e10adc3949ba59abbe56e057f20f883e","test203@163.com")

```php
$data = array(
	'user_name' => 'test203',
	'password' => md5(123456),
	'email' => 'test203@163.com'
);
$this->db_users->insert($data);
```

### 54、通过属性添加数据

基于 ORM 的添加
通过属性映射的方式 添加数据
INSERT INTO ecs_users(`user_name`,`password`,`email`)VALUES ("test204","e10adc3949ba59abbe56e057f20f883e","test204@163.com")

```php
$this->db_users->user_name = 'test204';
$this->db_users->password = md5(123456);
$this->db_users->email = 'test204@163.com';
$this->db_users->insert();
```

### 55、test_batch_insert(批量添加数据)

当需要批量添加数据时可以使用 batch_insert 方法
INSERT INTO ecs_users(`user_name`,`password`,`email`)VALUES ("test205","e10adc3949ba59abbe56e057f20f883e","test205@163.com")
INSERT INTO ecs_users(`user_name`,`password`,`email`)VALUES ("test206","e10adc3949ba59abbe56e057f20f883e","test206@163.com")

```php
$data = array(
		array(
		'user_name' => 'test205',
		'password' => md5(123456),
		'email' => 'test205@163.com'
	),
	array(
		'user_name' => 'test206',
		'password' => md5(123456),
		'email' => 'test206@163.com'
	),
);
$this->db_users->batch_insert($data);
```

### 56、test_peplace(判断是否重复插入，重复即为更新该条记录)

replace 使用 sql 语句中的 REPLACE 的指令,如果发现表中存在此行数据(根据主键或 者唯一索引判断)则执行替换操作,否则为新增操作。
如果表中存在 user_id 为 10 的主键记录,则更新原有记录
REPLACE INTO ecs_users(`user_id`,`user_name`,`password`,`email`)VALUES (15,"test010","e10adc3949ba59abbe56e057f20f883e","test010@qq.com")

```php
$data = array(
	'user_id' => 15,
	'user_name' => 'test010',
	'password' => md5(123456),
	'email' => 'test010@qq.com'
);
$this->db_users->replace($data);
```

### 57、test_update(更新数据库，以数组形式传参)

UPDATE 更新操作 要求必须输入条件,如果参数中有主键则系统会自动以这个主键值为条件。
说明
\1. 自动过滤掉非法字段
\2. 自动进行数据安全处理
\3. 默认以 $_POST 数据更新
\4. 如果参数中存在主键值将以这个值为条件进行更新数据
没有指定参数将以 $_POST 为参数进行更新,所以 $_POST 必须有值,并且必须有主键
值,否则不进行更新,这样可以很好的保证数据不被误操作更新
UPDATE `ecs_users` SET `user_id`=14,`password`="e10adc3949ba59abbe56e057f20f883e",`email`="test100@qq.com" WHERE user_id = 14

```php
$_POST = array(
	'user_id' => '14',
	'password' => md5(123456),
	'email' => 'test100@qq.com'
);
$this->db_users->update();
```

### 58、test_where_update(更新表中满足条件的某条记录)

插入的数据 user_id 为主键
UPDATE `ecs_users` SET `user_id`=14,`password`="e10adc3949ba59abbe56e057f20f883e",`email`="test100@gmail.com" WHERE user_id = 14

```php
$data = array(
	'user_id' => '14',
	'password' => md5(123456),
	'email' => 'test100@gmail.com'
);
$this->db_users->update($data);
```

### 59、test_where_update(通过属性修改表中满足条件的某条记录)

通过 ORM 对象映射修改数据
UPDATE `ecs_users` SET `user_name`="test101" WHERE user_name = "test010"

```php
$this->db_users->where = 'user_name = "test010"';
$this->db_users->user_name = 'test101';
$this->db_users->update();
```

### 60、test_inc(将满足条件的某条记录的某个字段做增加修改)

inc() 增加值
将 user_id=6 的记录 visit_count 加 1
UPDATE ecs_users SET visit_count=visit_count+1 WHERE user_id=6

```php
$this->db_users->inc('visit_count', 'user_id=6', 1);
```

### 61、test_dec(将满足条件的某条记录的某个字段做减少修改)

dec() 减少值
将 user_id=6 的记录 visit_count 减 1
UPDATE ecs_users SET visit_count=visit_count-1 WHERE user_id=6

```php
$this->db_users->dec('visit_count', 'user_id=6', 1);
```

### 62、test_delete(删除表中指定主键的某条记录)

删除数据时必须指定条件,这也是为了屏蔽误删除,如果以 $_POST 传参时存在主键,则删除这个主键的记录。
删除主键为 22 的记录,如果删除成功返回受影响的记录数
DELETE FROM ecs_users WHERE `user_id`=22

```php
$this->db_users->delete(22);
```

### 63、test_delete(删除表中满足条件的多条记录，以数组形式传参)

删除主键为 20、19、18、17 的数据,并返回受影响的记录数
DELETE FROM ecs_users WHERE user_id IN(20,19,18,17)

```php
$this->db_users->delete(array(20,19,18,17));
```

### 64、test_where_delete(删除表中满足条件的所有记录)

删除 user_id > 2 的所有记录
DELETE FROM ecs_users WHERE user_id > 15

```php
$this->db_users->where('user_id > 15')->delete();
```

### 65、test_delete(删除表中满足条件的所有记录，以数组形式)

在 delete 方法可以指定任何的可以用于 where 方法的参数,有关 where 参数要求请参看 where 部分
DELETE FROM `ecs_admin_log` WHERE log_id > 9 AND log_id < 30

```php
$this->db_admin_log->delete(array('log_id > 9', 'log_id < 30'));
```

### 66、test_field_exists(判断表中是否存在某个字段)

判断表中字段是否在存在 field_exists

```php
$this->db_admin_log->field_exists('user_id');
```

### 67、test_table_primary(获取表中的主键)

获取表的主键字段

```php
$this->db_admin_log->table_primary();
```

### 68、test_table_fields(获取表中的所有字段)

获取表的字段数组

```php
$this->db_admin_log->table_fields();
```

### 69、test_table_exists(判断是否存在某张表)

判断表是否存在

```php
$this->db_admin_log->table_exists('users');
```

### 70、test_find_last_sql/last_affected_rows/version

获得最后一条 SQL 语句 last_sql()
获得受影响的行数 last_affected_rows()
获得数据库版本信息 version()

```php
$this->db_vote->find();
$this->db_admin_log->find();
$this->db_vote->last_sql();
$this->db_vote->last_affected_rows();
$this->db_vote->version();
```

### 71、test_all_sqls(获取所有的sql语句)

获得所有 SQL 语句 all_sqls()

```php
$this->db_vote->all_sqls();
```

### 72、test_last_insert_id(获取最后插入的记录的id)

获得最后插入的主键 ID 值 last_insert_id()
INSERT INTO ecs_vote(`vote_name`,`start_time`,`end_time`)VALUES ("你是怎么知道我的？",1397023984,1399615984)

```php
$data = array(
	'vote_name' => '你是怎么知道我的？',
	'start_time' => SYS_TIME,
	'end_time' => SYS_TIME + (3600*24*30),
);
$this->db_vote->insert($data);
$this->db_vote->last_insert_id();
```

### 73、test_table_size(获取当前表的大小)

获得数据库当前表的大小 table_size()
获得表 users 表与 vote 、admin_log 表的大小 table_size(array('ecs_users', 'ecs_vote', 'ecs_admin_log'))
获得数据库当前前缀的所有表的大小 database_size()
获得数据库所有表的大小 database_size(true)

```php
$this->db_users->table_size();
$this->db_users->table_size('admin_log');
$this->db_users->table_size(array('users', 'vote', 'admin_log'));
$this->db_admin_log->database_size();
$this->db_admin_log->database_size(true);
```

### 74、test_table_info(获取当前表的信息)

获得表信息 table_info()
获得当前数据库的当前表信息 table_info()
获得指定表 users,vote,admin_log 的信息 table_info(array('users', 'vote', 'admin_log'))

```php
$this->db_users->table_info();
$this->db_users->table_info('users');
$this->db_users->table_info(array('users', 'vote', 'admin_log'));
```

### 75、test_database_tables(获得数据库当前前缀的所有的表 )

获得数据库当前前缀的所有的表 database_tables()
获得数据库所有的表 database_tables(true)

```php
$this->db_users->database_tables();
$this->db_users->database_tables(true);
```

### 76、test_create_database(创建一个新的数据库)

创建数据库 create_database()
以 utf8 编码创建数据库 ecjia
CREATE DATABASE IF NOT EXISTS `ecjia` CHARSET utf8

```php
$this->db->create_database('ecjia');
```

### 77、test_truncate(清空表的数据)

清空数据表 truncate(‘table’)

```php
$this->db->truncate(array('vote', 'vote_log'));
```

### 78、test_repair(一次修复多个数据表)

一次修复多个数据表 repair(‘table1’,‘table2’)

```php
$this->db->repair(array('vote', 'vote_log'));
```

### 79、test_optimize(一次优化多个数据表)

一次优化多个数据表 optimize(‘table1’,‘table2’)

```php
$this->db->optimize(array('vote', 'vote_log'));
```

### 80、test_rename(修改表名)

修改表名 rename(‘table1’,‘table2’)

```php
$this->db->rename(array('vote', 'vote_log'));
```

### 81、test_drop_table(一次删除多个数据表)

一次删除多个数据表drop_table()

```php
$this->db->drop_table(array('vote', 'vote_log'));
```

### 82、设置自动提交 beginTrans()

如果要完成数据库的事务处理需要选择合适的表引擎如 InnoDB、NDB、BDB 这是进行 事务处理的前提

```php
$data = array('wages' => 100);
$this->db_vote->begin_trans();  // 开启事务
$this->db_vote->add($data);		// 添加数据
$this->db_vote->commit(); 		// 提交事务
```

### 83、事务回滚 rollback()

当事务完整性被破坏或者其他原因可以通过 rollback() 方法放弃本次事务操作

```php
$data = array('wages' => 100);
$this->db_vote->begin_trans();	// 开启事务
$this->db_vote->add($data);		// 添加数据
$this->db_vote->rollback();		// 放弃本次提交
```

### 84、提交事务 commit()

如果整个事务完成正确可以通过 commit() 进行事务的提交完成最终操作

```php
$data = array('wages' => 100); 	
$this->db_vote->begin_trans();	// 开启事务	
$this->db_vote->add($data);		// 添加数据
$this->db_vote->commit();		// 提交本次事务
```

### 85、批量执行 SQL 语句 runSql()

注：1. 每条 SQL 语句必须以换行结束,否则系统无法拆分各个 SQL 语句
\2. 不允许有 SQL 注释如 #

```php
$file= file_get_contents('sql.sql');//sql.sql 为 SQL 语句文件
$this->db->execute_sql($file);
```

### 86、开关触发器 trigger

如果设置了触发器默认 CURD 都会执行,但有时有些动作不希望激活触发器,这时可 以使用 trigger 方法开启或关闭。
开启触发器,系统默认就是开启的

```php
$this->db_vote->trigger(true);
```

### 87、关闭触发器

```php
$this->db_vote->trigger(false);
```

### 88、关联模型中使用查询语句

```php
$db = RC_Loader::load_app_model('vote_relmodel');
$db->join = array(
// 关联表模型（表名）
'vote_option' => array(
'type' 			=> HAS_MANY,				// 包含一条主表记录			
'parent_key' 	=> 'vote_id',				// 关联字段
'foreign_key' 	=> 'vote_id',				// 关联字段
'field' 		=> 'option_id|id, option_name|name', 		// 查询字段
'model'	=> RC_Loader::load_app_model('vote_option_model'),
```

### 89、test_join (关联查询)

```php
$data2 = $db->join('vote_option')->select();// 只关联 vote_option 表
$data3 = $db->join(array('vote_option', 'vote_log'))->select(); // 关联 vote_option 表与 vote_log 表
```

### 90、HAS_ONE(包含一条记录)

因为结果是一维数组,有同名字段为覆盖,所以最好定义 field 属性,然后起别名

```php
$db = RC_Loader::load_app_model('goods_relmodel');
$data = $db->join('goods_activity')->select();
```

### 91、只匹配关联表中的部分字段

关联 goods_activity 表 , 只筛选 act_id,act_name,act_desc,act_type 字段, act_type 字段起别名为 type

```php
$db = RC_Loader::load_app_model('goods_relmodel');
$db->join = array(
// 关联表
'goods_activity' => array(
'type' 			=> HAS_ONE,		// 包含一条主表记录
'parent_key' 	=> 'goods_id',	// 主表字段
'foreign_key' 	=> 'goods_id',	// 关联字段
'field'			=> 'act_id, act_name, act_desc, act_type|type',	// 关联表检索的字段
'model' 		=> RC_Loader::load_app_model('goods_activity_model'),
),
);
$data = $db->join('goods_activity')->select();
```

### 92、关联 goods_activity 表 , 只筛选 act_id,act_name,act_desc,act_type 字段, act_type 字段起别名为 type

```php
$db = RC_Loader::load_app_model('goods_relmodel');
$data = $db->field('goods_id, goods_name, goods_sn')->where('goods_id > 19')->order('goods_id DESC')->select();
```

### 93、HAS_MANY(包含多条记录)

HAS_MANY 与 HAS_ONE 基本一样。HAS_ONE 中返回一维数组,HAS_MANY 返回 多维数组

```php
$db = RC_Loader::load_app_model('goods_relmodel');
$db->join = array(
'goods_gallery' => array(
'type' 			=> HAS_MANY,
'parent_key' 	=> 'goods_id',
'foreign_key' 	=> 'goods_id',
'field' 		=> 'img_url, thumb_url, img_original',
'model'			=> RC_Loader::load_app_model('goods_gallery_model'),
),
);
$data = $db->field('goods_id, goods_name, goods_sn')->select();
```

### 94、BELONGS_TO( 被包含)

比如说栏目表与文章表进行关联,文章表中每一条记录都有栏目表中的 id,如果指定文 章表为主表,那么栏目表中与文章表间的关系就是 BELONGS_TO,意思为栏目表中有一个 字段保存在文章表中
BELONGS_TO 定义与 HAS_MANY 定义相反，具体操作与HAS_MANY、HAS_ONE 是一样的,只需要理解这是一个角色互换就可以了,也就是说 HAS_MANY 可以用 BELONGS_TO 实现、BELONGS_TO 也可以用 HAS_MANY 实现。

```php
$db = RC_Loader::load_app_model('article_relmodel');
$db->join = array(
// 关联表
'article_cat' => array(
'type' 			=> BELONGS_TO,		// 包含一条主表记录
'parent_key' 	=> 'cat_id',	// 主表字段
'foreign_key' 	=> 'cat_id',	// 关联字段
'field'			=> 'cat_id|catid, cat_name|catname',
'model' 		=> RC_Loader::load_app_model('article_cat_model'),
),
);
$data = $db->select();
```

### 95、MANY_TO_MANY 多对多关联操作

一般情况下将多对多转化为多个一对多关系,这样操作起来更方便,比如说,用户表与用户组表,一个用户可以属于多个用户组,一个用户组也可以有多个用户,那么这种场景下的关系就是典型的多对多关系
注意:
中间表的关联字段必须与关联的两张表字段名相同
关于多对多关系需要特殊指定的属性如下 relation_table:多对多关联的中间表

```php
$db = RC_Loader::load_app_model('goods_relmodel');
$db->join = array(
'article' => array(
'type' 				=> MANY_TO_MANY,
'relation_table' 	=> 'goods_article',
'parent_key' 		=> 'goods_id',
'foreign_key' 		=> 'article_id',
'model'				=> RC_Loader::load_app_model('article_model'),
),
);
$data = $db->field('goods_id, goods_name')->select();
```

### 96、关联添加

一对一添加操作 HAS_ONE

```php
INSERT INTO ecs_goods(`goods_name`,`goods_desc`,`cat_id`)VALUES ("测试商品","测试商品测试商品测试商品测试商品测试商品",3)
INSERT INTO ecs_goods_activity(`act_name`,`act_desc`,`act_type`,`goods_id`)VALUES ("夺宝奇兵之测试商品","夺宝奇兵之测试商品夺宝奇兵之测试商品夺宝奇兵之测试商品",1,46)
返回值是  Array ( [goods] => 46 [goods_activity] => 19 )  即两个表最后自增加的 ID 组成的数组
```

### 97、一对多关联操作 HAS_MANY

即在对一张表进行一条记录插入时,同时对其他表插入多条记录
注:从表数据必须是二维数组

```php
INSERT INTO ecs_goods(`goods_name`,`goods_desc`,`cat_id`)VALUES ("测试商品2","测试商品测试商品测试商品测试商品测试商品2",3)
INSERT INTO ecs_goods_gallery(`img_url`,`thumb_url`,`img_original`,`goods_id`)VALUES ("images/200905/goods_img/9_P_1241511871575.jpg","images/200905/thumb_img/9_thumb_P_1241511871787.jpg","images/200905/source_img/9_P_1241511871749.jpg",47)
INSERT INTO ecs_goods_gallery(`img_url`,`thumb_url`,`img_original`,`goods_id`)VALUES ("images/200905/goods_img/9_P_1241511871575.jpg","images/200905/thumb_img/9_thumb_P_1241511871787.jpg","images/200905/source_img/9_P_1241511871749.jpg",47)
INSERT INTO ecs_goods_gallery(`img_url`,`thumb_url`,`img_original`,`goods_id`)VALUES ("images/200905/goods_img/9_P_1241511871575.jpg","images/200905/thumb_img/9_thumb_P_1241511871787.jpg","images/200905/source_img/9_P_1241511871749.jpg",47)
INSERT INTO ecs_goods_gallery(`img_url`,`thumb_url`,`img_original`,`goods_id`)VALUES ("images/200905/goods_img/9_P_1241511871575.jpg","images/200905/thumb_img/9_thumb_P_1241511871787.jpg","images/200905/source_img/9_P_1241511871749.jpg",47)
Array ( [goods] => 47 [goods_gallery] => Array ( [0] => 44 [1] => 45 [2] => 46 [3] => 47 ) ) 
```

### 98、BELONGS_TO 关联插入

BELONG_TO 可以理解为与 HAS_MANY 或 HAS_ONE 的反意,只是角色的互换

```php
INSERT INTO ecs_article(`title`,`content`,`keywords`)VALUES ("手机套餐","手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐","手机,套餐")
INSERT INTO ecs_article_cat(`cat_name`,`cat_type`,`cat_desc`)VALUES ("手机套餐",1,"手机套餐分类")
UPDATE `ecs_article` SET `cat_id`=13 WHERE id=38
Array ( [article] => 38 [article_cat] => 13 ) 
```

### 99、MANY_TO_MANY

支持一次 MANY_TO_MANY 关联方式的插入操作

```php
INSERT INTO ecs_goods(`goods_name`,`goods_desc`,`cat_id`)VALUES ("测试商品3","测试商品测试商品测试商品测试商品测试商品3",15)
INSERT INTO ecs_article(`title`,`content`,`keywords`)VALUES ("手机套餐2","手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐2","手机,套餐")
INSERT INTO ecs_goods_article(`goods_id`,`article_id`,`admin_id`)VALUES (53,45,1)
Array ( [goods] => 53 [article] => 45 [goods_article] => 1 ) 
```

### 100、关联更新

HAS_ONE

```php
UPDATE `ecs_goods` SET `goods_id`=46,`goods_name`="测试商品4",`goods_desc`="测试商品测试商品测试商品测试商品4" WHERE goods_id = 46
SELECT goods_id FROM `ecs_goods` WHERE goods_id = 46 LIMIT 1 
SELECT act_id,act_name,act_desc,act_type AS type FROM `ecs_goods_activity` WHERE goods_id=46 LIMIT 1 
UPDATE `ecs_goods_activity` SET `act_name`="夺宝奇兵之测试商品4",`act_desc`="夺宝奇兵之测试商品夺宝奇兵之测试商品夺宝奇兵之测试商品4",`goods_id`=46 WHERE goods_id=46
Array ( [goods] => 1 ) 
```

### 101、一对多 HAS_MANY

一对多关联添加的使用方法与一对一是一样的

```php
UPDATE `ecs_goods` SET `goods_sn`="ECS000032" WHERE goods_id = 47 LIMIT 3 
SELECT goods_id FROM `ecs_goods` WHERE goods_id = 47 LIMIT 1 
SELECT img_url,thumb_url,img_original FROM `ecs_goods_gallery` WHERE goods_id=47
DELETE FROM `ecs_goods_gallery` WHERE goods_id=47
REPLACE INTO ecs_goods_gallery(`img_url`,`thumb_url`,`img_original`,`goods_id`)VALUES ("images/200905/goods_img/9_P_1241511871575.jpg","images/200905/thumb_img/9_thumb_P_1241511871787.jpg","images/200905/source_img/9_P_1241511871749.jpg",47)
Array ( [goods] => 1 ) 
```

### 102、BELONGS_TO

通过以上关联操作完成 article_cat 表与 article 表的关联更新操作,因为 article 表中保存 article_cat 表的记录,设置 article 表为主表所以关联类型为 BELONGS_TO

```php
UPDATE `ecs_article` SET `article_id`=40,`title`="手机套餐2",`content`="手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐手机套餐2" WHERE article_id = 40
SELECT article_id FROM `ecs_article` WHERE article_id = 40 LIMIT 1 
SELECT cat_id AS catid,cat_name AS catname FROM `ecs_article_cat` WHERE cat_id= LIMIT 1 
SELECT * FROM `ecs_article` WHERE `article_id`=40 LIMIT 1 
UPDATE `ecs_article_cat` SET `cat_name`="手机套餐2",`cat_type`=1,`cat_desc`="手机套餐分类2",`cat_id`=15 WHERE cat_id = 15
Array ( [article] => 1 [article_cat] => 1 ) 
```

### 103、关联删除

HAS_ONE 关联删除

```php
SELECT * FROM `ecs_goods` WHERE goods_id > 53
SELECT act_id,act_name,act_desc,act_type AS type FROM `ecs_goods_activity` WHERE goods_id=54 LIMIT 1 
SELECT act_id,act_name,act_desc,act_type AS type FROM `ecs_goods_activity` WHERE goods_id=55 LIMIT 1 
DELETE FROM `ecs_goods` WHERE goods_id > 53
DELETE FROM `ecs_goods_activity` WHERE goods_id=54
DELETE FROM `ecs_goods_activity` WHERE goods_id=55
Array ( [goods] => 1 [goods_activity] => 1 ) 
```

### 104、HAS_MANY 关联删除操作

HAS_MANY 在关联删除中与 HAS_ONE 意义一样,参数设置也一样
删除商品的同时,删除商品下的缩略图

```php
SELECT * FROM `ecs_goods` WHERE goods_id = 48
SELECT img_url,thumb_url,img_original FROM `ecs_goods_gallery` WHERE goods_id=48
DELETE FROM `ecs_goods` WHERE goods_id = 48
DELETE FROM `ecs_goods_gallery` WHERE goods_id=48
Array ( [goods] => 1 [goods_gallery] => 1 ) 
```

### 105、 多表视图

视图是虚表,是从一个或几个基本表(或视图)中导出的表,视图是原始数据库数据的 一种变换,是查看表中数据的另外一种方式。可以将视图看成是一个移动的窗口,通过它可 以看到感兴趣的数据。 视图是从一个或多个实际表中获得的。
SELECT * FROM ecs_goods INNER JOIN ecs_goods_activity ON ecs_goods.goods_id=ecs_goods_activity.goods_id LEFT JOIN ecs_goods_article ON ecs_goods.goods_id = ecs_goods_article.goods_id ORDER BY ecs_goods.goods_id DESC LIMIT 3

```php
$db = RC_Loader::load_app_model('goods_viewmodel');
$db->view = array(
		// 定义 goods_activity 表规则
		'goods_activity' => array(
			'type' => INNER_JOIN,  // 指定连接方式
			'field' => 'act_id, act_name, act_desc|desc', //act_desc 字段起别名 desc
			'on' => 'goods.goods_id=goods_activity.goods_id', // 关联条件
		),
		// 定义 goods_article 表规则
		'goods_article' => array(
			'type' => LEFT_JOIN,	// 指定连接方式
			'on' => 'goods.goods_id = goods_article.goods_id',	// 关联条件
			'field' => 'article_id|articleid,admin_id|adminid',
		),
);

$data = $db->limit(3)->order('goods.goods_id DESC')->select();
```

### 106、只使用某个视图定义

定义了多个视图,但是使用时只想使用某个视图定义,可以通过执行 join 方法
SELECT * FROM ecs_goods
SELECT * FROM ecs_goods INNER JOIN ecs_goods_activity ON ecs_goods.goods_id=ecs_goods_activity.goods_id
SELECT * FROM ecs_goods INNER JOIN ecs_goods_activity ON ecs_goods.goods_id=ecs_goods_activity.goods_id LEFT JOIN ecs_goods_article ON ecs_goods.goods_id = ecs_goods_article.goods_id

```php
$db = RC_Loader::load_app_model('goods_viewmodel');
不关联任何表
$data = $db->join(null)->select();

只关联 一个 表（只关联 goods_activity 表）
$data = $db->join('goods_activity')->select();

只关联其中 两个 表 (关联 goods_activity 表与 goods_article 表)
$data = $db->join(array('goods_activity', 'goods_article'))->select();
```

### 107、自动处理 create()

自动验证 create() 或 validate()

```php
$db = RC_Loader::load_app_model('users_model');
$db->validate = array(
array('username', 'nonull', '用户名不能为空', 2, 3),
);
```

### 108、自动完成 create() 或 auto()

```php
$db = RC_Loader::load_app_model('users_model');
$db->auto = array(
array('click', 'intval', 'function', 1, 2),
array('begin_time', 'strtotime', 'function', 2, 1),
);
```

### 109、字段自动映射 create() 或 map()

```php

```