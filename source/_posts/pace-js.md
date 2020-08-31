---
title: 给你的wordpress主题自由添加顶端页面加载进度条
date: 2019-08-03 23:20:13
tags: 
- 建站
- 插件
categories: 
- 折腾笔记
---
[![](https://i.loli.net/2019/07/24/5d385f0cdec3485992.png)](https://i.loli.net/2019/07/24/5d385f0cdec3485992.png)

> 都说了，折腾网站与折腾装修一样，都是一个自我“折磨”的过程，在这个过程中挖掘乐趣。

<!--more-->

前段时间，看了很多人的博客，发现有的博客有一个进度条，类似一些Safari之类的浏览器。效果看上去很不错，于是我也动心了，自己瞎折腾找教程。终于实现了这个功能。
在此记录下我的实现方式方法，一并记录。
（如下GIF是我网页的动态效果，如果你也想让你的网站拥有，请往下看）
[![](https://i.loli.net/2019/07/24/5d3859bb7041978979.gif)](https://i.loli.net/2019/07/24/5d3859bb7041978979.gif)
------------

开始的时候，在网上找寻，也不知道这个叫啥名字，直到我找到了WEB主题公园的这篇文章：<http://www.2zzt.com/jcandcj/7427.html>
但这篇文章主要是使用`css3+JQ`的方式实现的，其原理是一种“障眼法”，使用的是自动读秒的形式让一个进度条自动读完并消失，这样的做法好处是稳定，每个页面的读取时间相同，不经意间实现了高大上的效果，实乃装逼的不二选择。
但我主要是需要一个实时同步的，真实的能有效反馈加载情况的“进度条”，于是找到了今天的主角：
### pace.js ###
> pace.js是一个非常先进的JavaScript插件，可以实时监听页面的数据加载，包括Ajax请求，显示页面加载进度，并且能够定制样式，功能强大。

实现顶端加载进度条的方法非常简单，你甚至可以在任何主题中进行添加；
实现方法共三个步骤：

### 一、下载并上传pace.js到你的网站服务器目录 ###

------------

首先下载：[`pace.js`](https://pan.baidu.com/s/1RR8KfPLSQFfBgtBCnM2yQA)
把下载好的`pace.min.js`放至到你需要更改的主题的主题`~\assets\js`目录中.
(注意文件权限需要跟此目录下其余文件保持一致，下同！切记，切记！)
### 二、 修改主题模板的函数：###

------------
将如下代码放置到函数模板`functions.php`的最后位置：

```php
wp_enqueue_script( 'pace.min', get_theme_file_uri( '/assets/js/pace.min.js' ), array( 'jquery' ), '1.0', true );
```
(注意以上代码中`pace.min`以及`/assets/js/pace.min.js`,如需要更改文件名称则需要修改相对应的部分)
你可以直接在wordpress的仪表盘中修改，也可以直接后台修改文件，备份是必不可少的步骤，切记！
1）进入wordpress仪表盘->外观->主题->Theme Editor
2）选择右侧的函数模板`functions.php`
3）在最下方添加并保存
![](https://i.loli.net/2019/07/24/5d3800787670537575.jpg)
### 三、 添加样式代码到主题中 ###

------------

将如下的样式代码，添加到主题`style.css`的最后面:
（我在下面的代码中添加了注释，如果您不需要注释，请连同注释前后的`/* */`一并删除即可 ）
```css
.pace {
    -webkit-pointer-events: none;
    pointer-events: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
    -webkit-transition: opacity 0.8s ease-in-out;
    -moz-transition: opacity 0.8s ease-in-out;
    -o-transition: opacity 0.8s ease-in-out;
    transition: opacity 0.8s ease-in-out;
}
.pace-inactive {
    opacity: 0;
    filter: alpha(opacity=0);
}
.pace .pace-progress {
    background: #3690cf; /*此为HEX十六进制颜色码,您可以通过调节此处来更改颜色*/
    position: fixed;
    z-index: 2000;
    top: 0;
    right: 100%;
    width: 100%;
    height: 2px;/*此为高度2px的线条，如果您觉得不够粗，可以调节此处*/
}
```
如图，与之前一致，找到`style.css`，拉倒最后，增加代码
![](https://i.loli.net/2019/07/24/5d38581e5bfb667618.jpg)
完成添加，保存后，刷新网页查看顶部进度条效果。

该进度条，不是那种设定好固定的加载进度时间，单纯通过CSS3+简单JS实现的，而是真实呈现页面加载进度。
上面的样式代码只是最基础简洁的样式，你可以下载更多样式<https://github.com/HubSpot/pace>，
包括闪光灯、MAC OSX、左侧填充、顶部填充、计数器和弹跳等。
根据自己的喜好，分别将样式代码添加到主题style.css最后，将呈现不同的样式动画。
进阶设置请看pace官网：http://github.hubspot.com/pace/docs/welcome/
[![](https://i.loli.net/2019/07/24/5d3859d66e01427981.gif)](https://i.loli.net/2019/07/24/5d3859d66e01427981.gif)

Ps1:原作者的github已经3年没有更新了，不知道是已经足够好，还是说原作者不再更新。如有更好的代码我也会继续贴出~
Ps2:无论您是在wordpress仪表盘更改数据还是通过后台文件直接更改，请务必备份原始数据，这个进度条无法使用事小，导致你的网站打不开事大！
Ps3:如果更新后还是无法看到进度条效果，建议无论如何先去查查你的文件权限。必须权限一致才可以哟~

参考链接：<http://zmingcx.com/wordpress-theme-adds-page-load.html>