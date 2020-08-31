---
title: 使用transmission命令行工具集直接制作种子的方法
date: 2019-08-03 23:42:23
tags:
- NAS
- PT
- 做种
categories: 
- 关于PT的两三事
---
> 再次感谢老哥@hanwen的技术支持。如果您觉得此贴有用，还请留言支持我们.

之前看了坛子里大神的帖子，相信很多小伙伴与我一样，肯定安耐不住希望自己做种自己发布了吧？
我也是看了PT贴吧老哥的操作，才学会了上传的基本操作。

<!--more-->

奈何~手里只有一台安装了transmission的群晖，我又经常不在局域网内，故想是否能用transmission进行做种呢？
研究捯饬了一番，在司机老哥@hanwen的帮助下，又在transmission的官网[Wiki](https://help.ubuntu.com/community/TransmissionHowTo "Wiki")中查到了transmission做种的方法，现在分享给大家。
> 注意！此方法仅限于可编译的SHH环境，不管你是路由器，小钢炮，群晖，还是自购VPS，一定要有ROOT权限！建议全程使用putty进行，如何使用自行百度，不在本次讨论内！

第一步：使用find命令找到环境内的transmission安装位置。
命令：
```php
find / -name transmission-create
```
第二步：使用cd命令进入transmission的bin目录
命令：
```php
cd /你的地址/transmission/bin
```
第三步：使用ls命令检测bin目录内容
命令：
```php
ls
```

如果正常反馈，你会看到信息至少有一条显示：
```PHP
transmission-create
```
*（如果没有显示，请升级至transmission最新版本2.9.4）*

第四步：使用transmission-create命令行制作你的种子
例子：
```PHP
./transmission-create -p -o /你要输出的种子文件位置/你要输出的种子名称.torrent -t 你需要的Tracker服务器的URL是 -s 2048 /你需要做种原文件的位置 -c 你的备注 &
```

参数
```PHP
-p 表示这是私用的种子，PT的话这个必须要加上；
-o 生成的种子输出位置，不要忘记把名字打上；
-t tracker的地址，我用的老师站的tracker的做范本，如果大家需要做其他PT站的种子，请自行修改
-s 每个文件块的大小，单位是KB，我设置的是2M，也就是2048KB
-c 表示备注，可以添加你自己的标注，这里建议添加自己喜欢的备注名称
```
最后空一格写源文件的位置，也就是文件的存放位置，可以是一个文件或者一整个目录
最后可以空一行加一个&，这样即使关掉窗口也可以在后台运行
填完，回车，种子就在制作了。种子制作完成后，会显示一个
```PHP
done！
```
然后你就可以打开你的资源管理器看到这个种子文件了。

如果你还是不放心的话，可以登陆网站[https://tool.lu/torrent](https://tool.lu/torrent)来查看种子内容。

> 如果你制作的种子名称或者目录中有中文，不妨试试以下这条命令；

```PHP
export LC_ALL='zh_CN.utf8
```

> 注意，此命令不会返回任何结果。


