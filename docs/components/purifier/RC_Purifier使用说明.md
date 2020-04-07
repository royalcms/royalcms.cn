### Ecjia后台RC Purifier使用说明

[跳到导航](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#mw-head)[跳到搜索](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#p-search)

#### 目录



- [1HTML Purifier 简介](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#HTML_Purifier_.E7.AE.80.E4.BB.8B)
- [2语法](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#.E8.AF.AD.E6.B3.95)
- [3配置](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#.E9.85.8D.E7.BD.AE)
- [4使用示例](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明#.E4.BD.BF.E7.94.A8.E7.A4.BA.E4.BE.8B)

#### HTML Purifier 简介[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明&action=edit&section=1)]

[HTML Purifier](http://htmlpurifier.org/) 是一个用 PHP 编写的标准、兼容的 HTML 过滤器，支持自定义标签、属性、过滤规则。 可以有效的防止 XSS 攻击！

#### 语法[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明&action=edit&section=2)]

```
 RC_Purifier::clean($dirty, $config = null);
 $dirty Array or String 
 $config Array or String 
```

#### 配置[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明&action=edit&section=3)]

```
  $config = [
    'HTML.Doctype'             => 'XHTML 1.0 Strict',
    'HTML.Allowed'             => 'div,b,strong,i,em,a[href|title],ul,ol,li,p[style],br,span[style],img[width|height|alt|src]',//保留的html标签[允许的属性]
    'CSS.AllowedProperties'    => 'font,font-size,font-weight,font-style,font-family,text-decoration,padding-left,color,background-color,text-align',//保留的css属性
    'AutoFormat.AutoParagraph' => true, //格式化-自动添加段落标签，前提是必须允许P标签的使用
    'AutoFormat.RemoveEmpty'   => true,//格式化-清除空标签
    'Attr.EnableID' => true,
    'HTML.SafeIframe' => 'true',
    'URI.SafeIframeRegexp' => "%^(http://|https://|//)(www.youtube.com/embed/|player.vimeo.com/video/)%",
  ]
```

更多参考：http://htmlpurifier.org/live/configdoc/plain.html

#### 使用示例[[编辑](http://wiki.shangchina.com/index.php?title=Ecjia后台RC_Purifier使用说明&action=edit&section=4)]

```
 RC_Purifier::clean(Input::get('inputname'));
 RC_Purifier::clean('This is my H1 title', 'titles');
 RC_Purifier::clean('This is my H1 title', array('Attr.EnableID' => true));
```


配置可根据情况扩展