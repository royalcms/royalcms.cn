### ecjia后台RC_Lang使用说明以及语言包升级说明



#### 目录

 [隐藏] 

- [1一、语言包文件中定义更新](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Lang使用说明以及语言包升级说明#.E4.B8.80.E3.80.81.E8.AF.AD.E8.A8.80.E5.8C.85.E6.96.87.E4.BB.B6.E4.B8.AD.E5.AE.9A.E4.B9.89.E6.9B.B4.E6.96.B0)
- [2二、控制器文件中语言包用法更新](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Lang使用说明以及语言包升级说明#.E4.BA.8C.E3.80.81.E6.8E.A7.E5.88.B6.E5.99.A8.E6.96.87.E4.BB.B6.E4.B8.AD.E8.AF.AD.E8.A8.80.E5.8C.85.E7.94.A8.E6.B3.95.E6.9B.B4.E6.96.B0)
- [3三、模板文件中语言包用法更新](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Lang使用说明以及语言包升级说明#.E4.B8.89.E3.80.81.E6.A8.A1.E6.9D.BF.E6.96.87.E4.BB.B6.E4.B8.AD.E8.AF.AD.E8.A8.80.E5.8C.85.E7.94.A8.E6.B3.95.E6.9B.B4.E6.96.B0)
- [4四、system系统中语言包升级方法](https://www.ecjia.com/wiki/ECJiaWiki:Ecjia后台RC_Lang使用说明以及语言包升级说明#.E5.9B.9B.E3.80.81system.E7.B3.BB.E7.BB.9F.E4.B8.AD.E8.AF.AD.E8.A8.80.E5.8C.85.E5.8D.87.E7.BA.A7.E6.96.B9.E6.B3.95)

#### 一、语言包文件中定义更新

旧：

```
$LANG['log_id'] = '编号';
$LANG['js_languages']['select_date_value'] = '如果您要清除日志,请选择清除的日期';
```

新：

```
  return array(
      'log_id'        => '编号',
      'js_languages'  => array(
          'select_date_value' => '如果您要清除日志,请选择清除的日期',
      ),
  );
```

#### 二、控制器文件中语言包用法更新

```
 旧：'total_records' => RC_Lang::lang('total_records'),
 新：'total_records' => RC_Lang::get('system::system.total_records'),
 备注：get('应用模块名称'::'语言包文件名称'.'键名')
```

#### 三、模板文件中语言包用法更新

```
 第一种情况：
 旧： {$lang.unread}
 新： {lang key='system::check_file_priv.unread'}
 备注：{lang key='应用模块名称'::'语言包文件名称'.'键名'}
 第二种情况：
 旧：
 新：
 备注：此时需要在控制其中添加如下
 $this->assign('cfg_range_lang', RC_Lang::get('system::shop_config.cfg_range'));
 模板中赋值即可
```

#### 四、system系统中语言包升级方法

```
 首先在①控制器使用：__('中文') ②模板中使用：{t}中文{/t}
 其次使用poedit软件打开后缀为po的语言包文件，进行相应的中引文翻译保存即可。
```