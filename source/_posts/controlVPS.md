---
title: 控制你的VPS
date: 2019-08-04 15:35:34
tags:
- VPS
- 建站
categories:
- 折腾笔记
---
也许你的VPS已经安装完成了，但是你要如何控制你的VPS呢？
在这里推荐如下几款软件（win平台和Android平台）给大家。基本算是管理VPS必装软件。

![SSH][1]
<!--more-->


 **1. PuTTY（远程登录Linux命令行神器）**
PuTTY是一个免费的、开源的，在win平台下的telnet、rlogin和ssh客户端。在各种远程登录工具中，个人认为是最出色的那个（没错，我就是在针对你“**Xshell**”，怎么滴！）用PuTTY来管理远程Linux客户端（VPS）那可是极好极好的~~

基于各种各样的原因，在这里我不会放软件的下载链接，请各位自行搜（百）索（度）。
各种各样的原因：[苹果Xcode后门事件][2]

什么？链接文章太长不想看？
我来总结下：
 1. 后门可以任意读取你所发送的数据，如果他想的话。（包括账号和密码！）
 2. 如果把一个后门比作毒药，当你下载的控制/编辑软件带后门的话就等于你家炒菜的锅上涂满了毒药。（怎么能不中招？）
 3. 想防止下载带后门的软件请支持正版（至少是正版渠道）。

下载了PuTTY后，你将会获得如下7个程序：
 1. **PuTTY (主程序，点击它就对了)**
 2. PSCP (SCP 客户端, 命令行下通过 SSH 拷贝文件，类似于 Unix/Linux 下的 scp 命令)
 3. PSFTP (SFTP 的命令行客户端，类似于 FTP 的文件传输，只不过使用的是 SSH 的 22 端口，而非 FTP 的 21 端口，类似于 Unix/Linux 下的 sftp 命令)
 4. PuTTYtel (仅仅是一个 Telnet 客户端)
 5. Plink (命令行工具，执行远程主机上的命令)
 6. Pageant (PuTTY、PSCP、Plink 的 SSH 认证代理，用这个可以不用每次都输入口令了)
 7. PuTTYgen (用来生成 RSA 和 DSA 密钥的工具)
打开主程序后你将会看见如下软件窗口：

![PuTTY][3]

参照链接：[怎样利用PuTTY登陆SSH主机方法][4]
**注意：在命令框（黑色框框）中输入的密码是不显示的，按照你设定的密码输入即可**
登陆成功即会显示 `[root@XXX ~]#` （XXX即你主机的名称）

 **2. WinSCP（win下使用SFPT的图形化开源工具）**
说白了，就是个图形化管理远程主机的图形化工作，和PuTTY一起使用，效果更佳。方面管理远程主机上的文件。上传/下载文件也方便--直接拖拽即可。
参考链接：[WinSCP使用方法教程][5]

**3. ConnectBot（Android下管理远程主机的命令行APP）**
手机直接下载：[Google paly][6] | [豌豆荚][7]
中文界面，很友好，操作与PuTTY相同。

圈里有句话：**工欲善其事，必先利其器。**
这句话对折腾er尤其有效！
*此文仅针对菜鸟小白们。老司机请赶紧飙车去（笑）*
P.s：想当年，只知道使用PuTTY的我，第一次发现WinSCP时那种“我X，我X”的感觉不想你也尝试~~

P.s的P.s：如果你非不听要用“Xshell”我也没办法[手动耸肩表情]



  [1]: http://images.51cto.com/files/uploadimg/20130306/1420520.jpg
  [2]: http://baike.baidu.com/item/%E8%8B%B9%E6%9E%9CXcode%E5%90%8E%E9%97%A8%E4%BA%8B%E4%BB%B6
  [3]: http://www.222o.com/uploads/allimg/110923/1-110923203506430.jpg
  [4]: http://jingyan.baidu.com/article/e73e26c0eb063324adb6a737.html
  [5]: http://jingyan.baidu.com/article/ed2a5d1f346fd409f6be179a.html
  [6]: https://play.google.com/store/apps/details?id=org.connectbot&hl=zh_CN
  [7]: http://www.wandoujia.com/apps/org.connectbot
