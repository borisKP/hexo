---
title: 代码高亮插件Prismjs
date: 2019-08-03 23:39:31
tags: 
- VPS
- 插件
categories: 
- 折腾笔记
---
之前写的这篇文章的时候，我使用的还是Typechp,现在因为此站点是挂靠在群晖上面的，所以此站点为了方便起见（其实就是懒，用docker安装宝塔也很快）就改用了[`WP Editor.md`][4]，这个插件自带Markdown编辑器,也自带代码高亮，完全符合正统Markdown编辑语言，作者[淮城一只猫][5]表示：“或许这是一个WordPress中最好，最完美的Markdown编辑器。”懒人如我表示赞同。

------------
考虑到今后自己的文章中可能会出现很多的代码，尤其是自己使用的是Typecho的部落格，Typecho的编辑器是html编辑，直接添加代码发表文章后，typecho就会直接把代码编译过来，这样无论你是copy还是阅读都很麻烦！
为了让代码显示的更加友好，特此使用了这款代码高亮插件。
<!--more-->

----------

话不多说，先看效果。如下是一段PHP链接MYSQL数据库代码。
不使用插件的效果：
原代码：
`<?php 
$connec=mysql_connect("localhost","root","root") or die("不能连接数据库服务器： ".mysql_error()); 
mysql_select_db("liuyanben",$connec) or die ("不能选择数据库: ".mysql_error()); 
mysql_query("set names 'gbk'"); 
?> `
使用插件的效果：
```PHP
<?php 
$connec=mysql_connect("localhost","root","root") or die("不能连接数据库服务器： ".mysql_error()); 
mysql_select_db("liuyanben",$connec) or die ("不能选择数据库: ".mysql_error()); 
mysql_query("set names 'gbk'"); 
?>
```

----------
>使用方法：
>在代码的上下加上````如下：
>
>    ```
>    你的代码
>    ```
>
>单行代码前后加上·如下：
>`·你的代码·`
>***注意：这个“·”符号在“键盘1”的左边，那个“~键”就是！***
----------


Prismjs插件下载：
[GitHub][1] | [Prismjs.1.0.3.zip][2]

想要说明的是：此款插件的编写作者是**木是伊**。原文地址如下：
[http://wiseclock.ca/code/prismjs-for-typecho.html][3]


  [1]: https://github.com/WiseClock/Prismjs
  [2]: http://www.wiseclock.ca/usr/uploads/2016/02/2805100268.zip
  [3]: http://wiseclock.ca/code/prismjs-for-typecho.html
  [4]: https://github.com/JaxsonWang/WP-Editor.md
  [5]: https://iiong.com/