---
title: 缩略的网站标志(角标)的制作--Favicon.ico
date: 2019-08-03 23:35:11
tags:
- 建站
categories: 
- 折腾笔记
---
自己制作一个网站，看着它在自己的手里慢慢变成自己所希望的样子，这个过程是美好的，也是愉悦的，比起枯燥的工作来说，让人充满了动力。
其实制作网站和装修一样，都是一个折腾，再折腾，又折腾的过程，让人着迷，后续有机会我也会更新些关于家装的分享帖（现在就挖坑真的好吗？）（笑） :joy: 

------------
本次要说的主要是"Favicon.ico",如下是一段关于favicon图标的介绍:

> ### favicon.ico一般用于作为缩略的网站标志，它显示在浏览器的地址栏、浏览器标签上或者在收藏夹上，是展示网站个性的缩略logo标志，也可以说是网站头像,目前主要的浏览器都支持favicon.ico图标，如果要让网站看起来更专业、更美、更有个性，favicon.ico是必不可少的，你在本站使用ICO图标转换工具就可以轻松将您的网站图标转换成favicon.ico。

 详细的介绍你也可以浏览如下链接:
[Favicon.ico的wiki百科][1]

简而言之:Favicon.ico就是可以让你的网页有如下的效果:
![Favicon.ico][2]
如上图的红色框,就是这个效果啦~

也许不是所有人都在乎这个标志，但在乎细节的人，他的网页上就一定有这个角标。

------------
分享一个制作  链接：
 >   [http://www.faviconico.org/][7]
 
下面是如何在您的网站中加入此图标的教程：

1. 如何使用Favicon.ico？
直接在你的主页中加入如下代码,然后把制作好的`Favicon.ico`放入你网站的根目录中即可.
注意，是放在你网站主页的 `<head> </head>`之间哟~
```html
	<link rel="shortcut icon" href="/favicon.ico"/>
	<link rel="bookmark" href="/favicon.ico"/>
```

2. 我的主页是`index.php`而不是`index.html`如何添加？
如果你和我一样，使用的是WordPress，那么好办，直接进入“仪表盘-外观-主题-对你当前使用的主题进行自定义”
![Favicon.wordpress.jpg][3]
对自定义主题进行“站点身份”管理，直接添加图片即可。
![zhuti1.jpg][4]  ![zhuti2.jpg][5]
如果你使用的不是WordPress，那么可能需要你要到网站的主页文件`index.php`看看他是如何引用的，再做更改，这里篇幅较长，不做说明


------------


如果你的网站favicon.ico 不起作用，或者是想要让favicon.ico 的兼容性更好，要使用下面几个步骤：

1：检查网站根目录下面的favicon.ico,也就是：`http://host/favicon.ico` 而不是`http://host/some/favicon.ico`
(该图标的路径一定要使用绝对路径)
2：确保
```html
<link rel="shortcut icon" href="/favicon.ico"/>
<link rel="bookmark" href="/favicon.ico"/>
```
使用的是`http://host/favicon.ico` 而不是其他目录文件，并确认文件名一致

3：如果你的网站带端口，或者是测试版本的话，那么尤其要注意360等浏览器，它们在请求`favicon.ico` 的时候会忽略端口号的。

------------

如果你想看看别人（百度）都用的是什么`Favicon.ico`,伟大的Google已经帮你做好了，只需要点击如下的链接就可以看到，更换你所需要查看的站点替代`baidu.com`即可.
[https://www.google.com/s2/favicons?domain=baidu.com](https://www.google.com/s2/favicons?domain=baidu.com "https://www.google.com/s2/favicons?domain=baidu.com")

最后是我的favicon.ico，请各位查看~
(可能有些大哟)
![ziji.png][6]


[1]:https://zh.wikipedia.org/wiki/Favicon
[2]:https://i.loli.net/2019/07/16/5d2d8b8a4363b44299.jpg
[3]:https://i.loli.net/2019/07/16/5d2d8f33ba1e014081.jpg
[4]:https://i.loli.net/2019/07/16/5d2d8f96a33a718243.jpg
[5]:https://i.loli.net/2019/07/16/5d2d9013725cd58141.jpg
[6]:https://i.loli.net/2019/07/16/5d2da6af32b4e56335.png
[7]:http://www.faviconico.org/