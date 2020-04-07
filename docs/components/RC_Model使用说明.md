### ecjia后台RC_Model使用说明



#### 方法列表

| 编号 |     方法名     |      简单描述       |
| :--: | :------------: | :-----------------: |
|  1   |    model()     | 调用应用下的model类 |
|  2   | table_exists() |   检测表是否存在    |
|  3   | create_table() |       创建表        |
|  4   |  drop_table()  |       删除表        |

#### 方法详细说明

1、调用model：

```
RC_Model::model()
```

- 调用系统下的的admin_user_model，示例：

```
RC_Model::model('admin_user_model');
```

| 参数 |  类型  |     描述     |
| :--: | :----: | :----------: |
| file | string | 数据模型名称 |

- 调用商品下的goods_model，示例：

```
RC_Model::model('goods/goods_model');
```

|   参数   |  类型  |         描述          |
| :------: | :----: | :-------------------: |
| app/file | string | 应用名称/数据模型名称 |

2、检测表是否存在

```
RC_Model::make()->table_exists($table_name)
```

- 检测goods表是否存在，示例：

```
RC_Model::make()->table_exists('goods');
```

|    参数     |  类型  | 描述 |
| :---------: | :----: | :--: |
| $table_name | string | 表名 |

3、创建表

```
RC_Model::make()->create_table($table_name, $schemes, $engine = 'InnoDB', $charset = 'utf8mb4', $collate = 'utf8mb4_unicode_ci')
```

- 创建goods表，示例：

```
$table_name = 'goods';
$schemes = array(
    "`goods_id` int(11) unsigned NOT NULL AUTO_INCREMENT",
    "`goods_name` varchar(120) NOT NULL DEFAULT ''",
    "PRIMARY KEY (`goods_id`)"
);
RC_Model::make()->create_table($table_name, $schemes);
```

|    参数     |  类型  |                描述                |
| :---------: | :----: | :--------------------------------: |
| $table_name | string |                表名                |
|  $schemes   | string |               表字段               |
|   $engine   | string |        表引擎（默认InnoDB）        |
|  $charset   | string |       字符集（默认utf8mb4）        |
|  $collate   | string | 排序规则（默认utf8mb4_unicode_ci） |

4、删除表

```
RC_Model::make()->drop_table($table_name)
```

- 删除goods表，示例：

```
RC_Model::make()->drop_table('goods');
```

|    参数     |  类型  | 描述 |
| :---------: | :----: | :--: |
| $table_name | string | 表名 |