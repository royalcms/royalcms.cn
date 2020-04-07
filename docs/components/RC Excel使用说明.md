#### 目录



- 1导入（Imports）
  - [1.1导入文件（load）](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.AF.BC.E5.85.A5.E6.96.87.E4.BB.B6.EF.BC.88load.EF.BC.89)
  - 1.2处理导入数据（get/all）
    - [1.2.1获取所有工作簿和行](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.8E.B7.E5.8F.96.E6.89.80.E6.9C.89.E5.B7.A5.E4.BD.9C.E7.B0.BF.E5.92.8C.E8.A1.8C)
    - [1.2.2获取第一行或第一个工作簿](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.8E.B7.E5.8F.96.E7.AC.AC.E4.B8.80.E8.A1.8C.E6.88.96.E7.AC.AC.E4.B8.80.E4.B8.AA.E5.B7.A5.E4.BD.9C.E7.B0.BF)
    - [1.2.3Workbook and sheet title](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#Workbook_and_sheet_title)
    - 1.2.4限制文件读取 分页
      - [1.2.4.1取多少行 takeRows](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.8F.96.E5.A4.9A.E5.B0.91.E8.A1.8C_takeRows)
      - [1.2.4.2跳过多少行 skipRows](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.B7.B3.E8.BF.87.E5.A4.9A.E5.B0.91.E8.A1.8C_skipRows)
      - [1.2.4.3takeColumns](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#takeColumns)
      - [1.2.4.4skipColumns](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#skipColumns)
      - [1.2.4.5数组对象转换](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E6.95.B0.E7.BB.84.E5.AF.B9.E8.B1.A1.E8.BD.AC.E6.8D.A2)
      - [1.2.4.6输出（dump,dd）](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.BE.93.E5.87.BA.EF.BC.88dump.2Cdd.EF.BC.89)
      - [1.2.4.7遍历 each foreach](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E9.81.8D.E5.8E.86_each_foreach)
  - [1.3选择工作簿和列](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E9.80.89.E6.8B.A9.E5.B7.A5.E4.BD.9C.E7.B0.BF.E5.92.8C.E5.88.97)
  - [1.4日期 Dates](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E6.97.A5.E6.9C.9F_Dates)
  - [1.5导出文件](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.AF.BC.E5.87.BA.E6.96.87.E4.BB.B6)
  - [1.6更改文件类型 convert](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E6.9B.B4.E6.94.B9.E6.96.87.E4.BB.B6.E7.B1.BB.E5.9E.8B_convert)
- 2输出 Exports
  - [2.1创建文件create](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.88.9B.E5.BB.BA.E6.96.87.E4.BB.B6create)
  - [2.2修改属性](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E4.BF.AE.E6.94.B9.E5.B1.9E.E6.80.A7)
  - 2.3导出Export
    - [2.3.1Excel5](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#Excel5)
    - [2.3.2Excel2007](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#Excel2007)
    - [2.3.3CSV](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#CSV)
  - [2.4存储store](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.AD.98.E5.82.A8store)
  - 2.5工作簿sheets
    - [2.5.1设置样式setStyle](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.AE.BE.E7.BD.AE.E6.A0.B7.E5.BC.8FsetStyle)
    - [2.5.2Fonts](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#Fonts)
    - [2.5.3Borders](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#Borders)
  - 2.6行Row
    - [2.6.1追加Append row](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.BF.BD.E5.8A.A0Append_row)
    - [2.6.2前置Prepend row](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.89.8D.E7.BD.AEPrepend_row)
  - 2.7单元格 cell
    - [2.7.1字体](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.AD.97.E4.BD.93)
    - [2.7.2边框](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.BE.B9.E6.A1.86)
    - [2.7.3对齐方式](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.AF.B9.E9.BD.90.E6.96.B9.E5.BC.8F)
  - [2.8冻结行列 Freeze](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.86.BB.E7.BB.93.E8.A1.8C.E5.88.97_Freeze)
  - 2.9设置宽高
    - [2.9.1列宽 setWidth](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.88.97.E5.AE.BD_setWidth)
    - [2.9.2行高 setHeight](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.A1.8C.E9.AB.98_setHeight)
    - [2.9.3设置单元格宽高](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.AE.BE.E7.BD.AE.E5.8D.95.E5.85.83.E6.A0.BC.E5.AE.BD.E9.AB.98)
    - [2.9.4自动宽高](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E8.87.AA.E5.8A.A8.E5.AE.BD.E9.AB.98)
  - [2.10合并单元格](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E5.90.88.E5.B9.B6.E5.8D.95.E5.85.83.E6.A0.BC)
  - [2.11格式化 setColumnFormat](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明#.E6.A0.BC.E5.BC.8F.E5.8C.96_setColumnFormat)

#### 导入（Imports）[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=1)]

##### 导入文件（load）[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=2)]

```
  RC_Excel::load('file.xls', function($reader) {

    // reader methods

  });
```

##### 处理导入数据（get/all）[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=3)]

#### 获取所有工作簿和行[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=4)]

```
RC_Excel::load('file.xls', function($reader) {

})->get();

or

RC_Excel::load('file.xls', function($reader) {

    // Getting all results
    $results = $reader->get();

    // ->all() is a wrapper for ->get() and will work the same
    $results = $reader->all();

});
```

###### 获取第一行或第一个工作簿[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=5)]

```
$reader->first();
```

###### Workbook and sheet title[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=6)]

```
// Get workbook title
$workbookTitle = $reader->getTitle();

foreach($reader as $sheet)
{
    // get sheet title
    $sheetTitle = $sheet->getTitle();
}
```

###### 限制文件读取 分页[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=7)]

###### 取多少行 takeRows[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=8)]

```
// You can either use ->takeRows()
$reader->takeRows(10);

// Or ->limitRows()
$reader->limitRows(10);
```

###### 跳过多少行 skipRows[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=9)]

```
// Skip 10 results
$reader->skipRows(10);

// Skip 10 results with limit, but return all other rows
$reader->limitRows(false, 10);

// Skip and take
$reader->skipRows(10)->takeRows(10);
```

###### takeColumns[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=10)]

```
// You can either use ->takeColumns()
$reader->takeColumns(10);

// Or ->limitColumns()
$reader->limitColumns(10);
```

###### skipColumns[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=11)]

```
// Skip 10 results
$reader->skipColumns(10);

// Skip 10 results with limit, but return all other columns
$reader->limitColumns(false, 10);

// Skip and take
$reader->skipColumns(10)->takeColumns(10);
```

###### 数组对象转换[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=12)]

```
$reader->toArray();
$reader->toObject();
```

###### 输出（dump,dd）[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=13)]

```
// Dump the results
$reader->dump();

// Dump results and die
$reader->dd();
```

###### 遍历 each foreach[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=14)]

```
// Loop through all sheets
$reader->each(function($sheet) {

    // Loop through all rows
    $sheet->each(function($row) {

    });
});
```

##### 选择工作簿和列[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=15)]

```
RC_Excel::selectSheets('sheet1')->load();
RC_Excel::selectSheets('sheet1', 'sheet2')->load();

//按顺序选择
// First sheet
RC_Excel::selectSheetsByIndex(0)->load();
// First and second sheet
RC_Excel::selectSheetsByIndex(0, 1)->load();

//选择列
// Select
$reader->select(array('firstname', 'lastname'))->get();
// Or
$reader->get(array('firstname', 'lastname'));
```

#### 日期 Dates[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=16)]

```
// Format the dates
$reader->formatDates(true);

// Disable date formatting
$reader->formatDates(false);

// Format dates + set date format
$reader->formatDates(true, 'Y-m-d');

//created_at
$rows->each(function($row) {
    $created_at = $row->created_at->format('Y-m-d');
});

//setDateColumns
$reader->setDateColumns(array(
    'created_at',
    'deleted_at'
))->get();

//设置默认日期格式
$reader->setDateFormat('Y-m-d');
```

##### 导出文件[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=17)]

```
RC_Excel::load('file.csv', function($file) {
    // modify stuff
})->export('csv');
```

##### 更改文件类型 convert[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=18)]

```
RC_Excel::load('file.csv', function($file) {
    // modify stuff
})->convert('xls');
```

#### 输出 Exports[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=19)]

#### 创建文件create[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=20)]

```
RC_Excel::create('Filename');

RC_Excel::create('Filename', function($excel) {
    // Call writer methods here
});
```

#### 修改属性[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=21)]

```
RC_Excel::create('Filename', function($excel) {
    // Set the title
    $excel->setTitle('Our new awesome title');
    // Chain the setters
    $excel->setCreator('Maatwebsite')
          ->setCompany('Maatwebsite');
    // Call them separately
    $excel->setDescription('A demonstration to change the file properties');
});
```

#### 导出Export[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=22)]

#### Excel5[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=23)]

```
RC_Excel::create('Filename', function($excel) {
})->export('xls');
// or
->download('xls');
```

#### Excel2007[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=24)]

```
->export('xlsx');
// or
->download('xlsx');
```

#### CSV[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=25)]

```
->export('csv');
// or
->download('csv');
```

#### 存储store[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=26)]

```
RC_Excel::create('Filename', function($excel) {
})->store('xls');

//指定路径
->store('xls', storage_path('excel/exports'));

//存储并导出
->store('xls')->export('xls');

//存储并发返回信息
->store('xls', false, true);
```

|  Key  |          说明           |
| :---: | :---------------------: |
| full  | Full path with filename |
| path  |  Path without filename  |
| file  |        Filename         |
| title |       File title        |
|  ext  |     File extension      |

#### 工作簿sheets[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=27)]

```
RC_Excel::create('Filename', function($excel) {
    $excel->sheet('Sheetname', function($sheet) {
        // Sheet manipulation
    });
})->export('xls');

//创建多个工作簿
RC_Excel::create('Filename', function($excel) {
    // Our first sheet
    $excel->sheet('First sheet', function($sheet) {
    });
    // Our second sheet
    $excel->sheet('Second sheet', function($sheet) {
    });
})->export('xls');

RC_Excel::create('Filename', function($excel) {
    $excel->sheet('Sheetname', function($sheet) {
        $sheet->fromArray(array(
            array('data1', 'data2'),
            array('data3', 'data4')
        ));
    });
})->export('xls');
```

#### 设置样式setStyle[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=28)]

```
// Set font with ->setStyle()`
$sheet->setStyle(array(
    'font' => array(
        'name'      =>  'Calibri',
        'size'      =>  15,
        'bold'      =>  true
    )
));
```

#### Fonts[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=29)]

```
//setFont 多属性设置
$sheet->setFont(array(
    'family'     => 'Calibri',
    'size'       => '15',
    'bold'       => true
));

//分别设置
// Font family
$sheet->setFontFamily('Comic Sans MS');

// Font size
$sheet->setFontSize(15);

// Font bold
$sheet->setFontBold(true);
```

#### Borders[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=30)]

```
// Sets all borders
$sheet->setAllBorders('thin');

// Set border for cells
$sheet->setBorder('A1', 'thin');

// Set border for range
$sheet->setBorder('A1:F10', 'thin');
```

#### 行Row[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=31)]

```
//操作第一行
$sheet->row(1, array(
     'test1', 'test2'
));

//第二行
$sheet->row(2, array(
    'test3', 'test4'
));

// 背景色
$sheet->row(1, function($row) {
    // call cell manipulation methods
    $row->setBackground('#000000');

});

//添加多行
$sheet->rows(array(
    array('test1', 'test2'),
    array('test3', 'test4')
));
```

#### 追加Append row[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=32)]

```
// 第二行后追加一行
$sheet->appendRow(2, array(
    'appended', 'appended'
));

// 追加到最后一行
$sheet->appendRow(array(
    'appended', 'appended'
));
```

#### 前置Prepend row[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=33)]

```
// 在第一行之前插入
$sheet->prependRow(1, array(
    'prepended', 'prepended'
));

// 插入最前面一行
$sheet->prependRow(array(
    'prepended', 'prepended'
));
```

#### 单元格 cell[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=34)]

```
$sheet->cell('A1', function($cell) {
    // 操作单个单元格
    $cell->setValue('data1');
});

$sheet->cells('A1:A5', function($cells) {
    // 操作范围内单元格
});

//设置背景色
$cells->setBackground('#000000');
```

#### 字体[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=35)]

```
// Set with font color
$cells->setFontColor('#ffffff');

// Set font family
$cells->setFontFamily('Calibri');

// Set font size
$cells->setFontSize(16);

// Set font weight to bold
$cells->setFontWeight('bold');

// Set font
$cells->setFont(array(
    'family'     => 'Calibri',
    'size'       => '16',
    'bold'       =>  true
));
```

#### 边框[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=36)]

```
// Set all borders (top, right, bottom, left)
$cells->setBorder('solid', 'none', 'none', 'solid');

// Set borders with array
$cells->setBorder(array(
    'top'   => array(
        'style' => 'solid'
    ),
));
```

#### 对齐方式[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=37)]

```
//水平居中
$cells->setAlignment('center');

//上下居中
 $cells->setValignment('center');
```

#### 冻结行列 Freeze[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=38)]

```
// 冻结第一行
$sheet->freezeFirstRow();

// 冻结第一列
$sheet->freezeFirstColumn();

// 冻结第一行和第一列
$sheet->freezeFirstRowAndColumn();

// Set freeze
$sheet->setFreeze('A2');
```

#### 设置宽高[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=39)]

#### 列宽 setWidth[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=40)]

```
//设置单列
$sheet->setWidth('A', 5);

//设置多列
$sheet->setWidth(array(
    'A'     =>  5,
    'B'     =>  10
));
```

#### 行高 setHeight[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=41)]

```
//单行
$sheet->setHeight(1, 50);

//多行
$sheet->setHeight(array(
    1     =>  50,
    2     =>  25
));
```



#### 设置单元格宽高[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=42)]

```
// 单个
$sheet->setSize('A1', 500, 50);

//多个
$sheet->setSize(array(
    'A1' => array(
        'width'     => 50,
        'height'    => 500
    )
));
```

#### 自动宽高[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=43)]

```
// Set auto size for sheet
$sheet->setAutoSize(true);

// Disable auto size for sheet
$sheet->setAutoSize(false);

// Disable auto size for columns
$sheet->setAutoSize(array(
    'A', 'C'
));
```

#### 合并单元格[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=44)]

```
//合并单元格
$sheet->mergeCells('A1:E1');

//合并列和行
$sheet->setMergeColumn(array(
    'columns' => array('A','B','C','D'),
    'rows' => array(
        array(2,3),
        array(5,11),
    )
));
```

#### 格式化 setColumnFormat[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Excel使用说明&action=edit&section=45)]

```
// 百分比
$sheet->setColumnFormat(array(
    'C' => '0%'
));

// Format a range with e.g. leading zeros前置0
$sheet->setColumnFormat(array(
    'A2:K2' => '0000'
));

// 多列格式化
$sheet->setColumnFormat(array(
    'B' => '0',
    'D' => '0.00',
    'F' => '@',
    'F' => 'yyyy-mm-dd',
));
 更多方法可参考PHPExcel
```