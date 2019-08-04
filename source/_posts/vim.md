---
title: Linux Shell基础命令-----vim
date: 2019-08-03 23:36:46
tags:
- 建站
- VPS
categories: 
- 折腾笔记
---
Shell是系统的用户界面，提供了用户与内核进行交互操作的一种接口。它接收用户输入的命令并把它送入内核去执行。
（[百度百科地址][1]）

<!--more-->

![VIM][2]

简单来说，我们使用 PuTTY 控制远程主机就使用的是shell命令。
在一众shell命令中，对我们菜鸟来说，最有用的就是`vim`了。
在所有的Linux发行版系统中，均内置了`vi`文书编辑器，但我们使用的`vim`不一定会存在。但是目前我们使用比较多的是 vim 编辑器，`vim` 具有程序编辑的能力，可以主动的以字体颜色辨别语法的正确性，方便程序设计。我们就需要安装ta。

 **1. vim的安装**

CentOS安装vim:`yum install vim`
Debian安装vim:`apt-get install vim`
Ubuntu安装vim:`sudo apt-get install vim-gtk`

*安装中如果需要任何依赖点击“y”即可*

以CentOS为例，当你的vim安装好后，在终端中输入`vim`即可看见如下画面（可能因按照时间/版本不同有差异）
```

~                              VIM - Vi IMproved
~
~                               version 7.4.629
~                           by Bram Moolenaar et al.
~                      Modified by <bugzilla@redhat.com>
~                 Vim is open source and freely distributable
~
~                        Become a registered Vim user!
~                type  :help register<Enter>   for information
~
~                type  :q<Enter>               to exit
~                type  :help<Enter>  or  <F1>  for on-line help
~                type  :help version7<Enter>   for version info
~

```
*输入“:q”退出即可。（如果不能退出请输入“:q!”）*

 **2. vim的使用**

基本上 vi/vim 共分为三种模式，分别是一般模式、编辑模式与指令列命令模式。 (这也是vim最难理解的部分)
*吐槽：麻蛋的一个文本编辑器都这么麻烦！一点都不如咱们win下的*.txt来的爽利*
这三种模式的作用分别是：
一般模式：
以 vi 打开一个档案就直接进入一般模式了(这是默认的模式)。在这个模式中， 你可以使用『上下左右』按键来移动光标，你可以使用『删除字符』或『删除整行』来处理档案内容， 也可以使用『复制、贴上』来处理你的文件数据。
编辑模式：
在一般模式中可以进行删除、复制、贴上等等的动作，但是却无法编辑文件内容的！ 要等到你按下『i, I, o, O, a, A, r, R』等任何一个字母之后才会进入编辑模式。注意了！通常在 Linux 中，按下这些按键时，在画面的左下方会出现『INSERT 或 REPLACE 』的字样，此时才可以进行编辑。而如果要回到一般模式时， 则必须要按下『Esc』这个按键即可退出编辑模式。
指令列命令模式：
在一般模式当中，输入『 : / ? 』三个中的任何一个按钮，就可以将光标移动到最底下那一行。在这个模式当中， 可以提供你『搜寻资料』的动作，而读取、存盘、大量取代字符、离开 vi 、显示行号等等的动作则是在此模式中达成的！

详细的命令及操作方式请直接百度：[点击链接][3]
在这里我仅介绍我们经常使用的部分：
使用vim打开某文件：
```
vim XXX**你的文件名称**
```
对于编辑器，首先介绍的必然是选择，复制，粘贴，删除，插入保存，退出等基层功能。
选择字符：v从光标当前位置开始，光标所经过的地方会被选中，再按一下v结束。 
选择整行：V从光标当前行开始，光标经过的行都会被选中，再按一下V结束。
标记区域：Ctrl+v从光标当前位置开始，选中光标起点和终点所构成的矩形区域，再按一下Ctrl+v结束。
删除字符：在一般模式下要删除一个字符，只需要将光标移到该字符上按下"x"；或者在编辑模式下直接“backspace”
删除整行：在一般模式下删除一整行内容使用"dd"命令。删除后下面的行会移上来填补空缺。
复制命令：选择你需要的部分在一般模式下按`y`（相当于win中的Ctrl+c）
粘贴命令：一般模式下，在光标位置点击`p`（相当于win中的Ctrl+v）
保存并退出：一般模式下输入`:wq`或者`ZZ`连续按下两次Z
退出不保存：`:q!` 强制退出并忽略所有更改(应该算指令模式下)

详细如何使用请参考[官方文档][4]或者搜索。（其实我也不全会）
如下是我找到的一张vim键位图，供大家参考！
*P.S：在vim中有大小写区分，请重点注意！*

![VI/VIM][5]


  [1]: http://baike.baidu.com/view/573462.htm
  [2]: http://ico.ooopic.com/ajax/iconpng/?id=105247.png
  [3]: http://baike.baidu.com/subview/113188/9338173.htm
  [4]: http://vim.wikia.com/wiki/Main_Page
  [5]: http://www.runoob.com/wp-content/uploads/2015/10/vi-vim-cheat-sheet-sch.gif
