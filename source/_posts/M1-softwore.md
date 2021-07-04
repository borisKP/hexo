---
title: 关于我使用的MacBook Air M1的软件
date: 2021-07-04 18:36:22
tags:
- macOS
categories:
- 折腾笔记
---

> 前因：
> 今年上半年的虚拟货币，让整个DIY市场已经完全畸形.
> 拿我个人举例子：
> 我19年双11买了张1660Ti显卡，当初买的2200元，在2021年初，在二手咸鱼市场上居然买了近3000+，这就简直了。电子消耗商品反向涨价。建议最近需要升级配置伙伴们多等等吧，已经~~高价~~买了的，安心用，早买早享受。

我也因为今年的虚拟货币异常，入手了一台16+256的低配MacBook Air M1版本。在使用了一段时间后，发现和之前intel平台还是有些许差异的，尤其是有些软件，根本不更新支持M1芯片（说的就是你[TotalFinder](https://totalfinder.binaryage.com/)），最近折腾了2周，终于完成了我的生产力工具平台搭建。

![apple-app-store-icon](https://i.loli.net/2021/07/04/wDWGYtHRn3cpKqs.jpg)

<!--more-->

**本文分为几个部分，主要是为了方便检索。**

## 生产力工具

关于生产力工具，因为每个人的工作流不同，只做个人推荐，人各有好嘛。

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|浏览器|Google Chrome|最强大的浏览器|是|免费|[官网](https://www.google.cn/intl/zh-CN/chrome/)|
|生产力|Microsoft 365|大名鼎鼎的苹果最佳开发者MS的好东西|是|269元/年（个人版）|[Mac App Store](https://apps.apple.com/cn/app-bundle/microsoft-365/id1450038993?mt=12)|
|虚拟机|Parallels Desktop 16.5|在Mac下安装完整的win系统(注意，只有16.5以上才支持M1芯片）|是|498元/年|[官网/数码荔枝](https://www.lizhi.io/product/parallels_desktop)|
|虚拟机|CrossOver 20|Mac操作系统的用户可以运行Windows系统的应用|否（可转译）|149元|[官网/麦软](https://www.crossoverchina.com/)|
## 清理类工具
知道为什么只买256G的Mac吗，因为升级需要1500元。就是穷，所以Mac也需要定期清理。

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|清理优化|Clean My Mac X|号称是Mac下最好用的磁盘清理软件|是|248元/年 or 588元买断| [官网](https://cleanmymac.com/) |
|清理优化|App Cleaner & Uninstaller Pro|深度清理应用残留， 完全卸载mac应用程序|是|US$19.90|[官网](https://nektony.com/mac-app-cleaner)|

## 媒体工具
除了强大的流媒体外，你当然也需要一款可以本地播放视频的软件，同时因为我的工作流有大量的图片浏览需求，而且每张图片都是只有几百kb的小图，这款轻量的图片浏览器足够轻，也足够快。其他的都太重了。

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|媒体工具|IINA|播放器，号称macOS下的 potplayer|否（可转译）|免费|[官网/GitHub](https://www.iina.io/)|
|媒体工具|Lyn for macOS|轻量级快速媒体图片浏览器|是|US$29.99|[官网](https://www.lynapp.com/)|
## 下载工具
无论是PC还是Mac，下载都是一个刚需，虽说现在的网速快到直接用Chrome也可以完美的下载完各个所需要的应用，但有以下3个痛点还是无法解决，正好就推荐如下3个工具使用。

1. 痛点：无法下载种子与磁力链接文件。
2. 痛点：无法下载流媒体网站视频内容。
3. 痛点：超高速与多线程下载内容。

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|下载工具|Folx|种子磁力下载工具|否（可转译）|98元|[官网/麦软](https://www.folxchina.cn/)|
|下载工具|Downie 4|视屏下载工具|是|US$19.99|[官网](https://software.charliemonroe.net/downie/)|
|下载工具|Neat Download Manager|用法相当于win下的IDM|是|免费|[官网](https://www.neatdownloadmanager.com/index.php/en/)|

## 连接工具
在Mac上，虽然有原生且强大的“终端”可以使用，不过再好的终端还是不能保存登陆信息一键登录，所以我们也需要一些连接工具用于连接远程或者局域网信息。
在win下我通常会使用putty与winscp这俩软件进行连接作业，在Mac下也有2个非常好用的替代品。
关于iMazing，如果你关注科技类新闻，当初M1刚推出的时候，很多人在M1上运行手机软件，用的就是这款软件，优秀性毋庸置疑，不过它的支付方式是：在电脑上验证激活码后，该激活码可绑定安装2台苹果移动设备，绑定移动设备后不可撤销。


|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|连接工具|Termius|好用的SSH连接客户端（最近转用开源的[iTerm2](https://iterm2.com/)）|是|38元/月|[Mac App Store](https://apps.apple.com/cn/app/termius-ssh-client/id1176074088?mt=12)|
|连接工具|Transmit 5|好用的FTP连接客户端，代替winscp|是|173元|[Mac App Store](https://apps.apple.com/cn/app/transmit-5/id1436522307?mt=12)|
|连接工具|iMazing|itunes完美替代品|是|119元/2个|[官网/麦软](https://imazing.com/zh)|

## 生产力工具拓展

有的人觉得Mac下使用系统自带的原生软件就好，不过我还是喜欢用这类第三方软件，极大提升我的工作效率

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|截图录像|iShot|截图，截长图，屏幕录像一个全包|是|免费|[Mac App Store](https://apps.apple.com/cn/app/ishot-%E4%BC%98%E7%A7%80%E7%9A%84%E6%88%AA%E5%9B%BE%E5%BD%95%E5%B1%8F%E5%B7%A5%E5%85%B7/id1485844094?mt=12)|
|解压软件|Better Zip|一款还不错的Mac平台下压缩解压软件，个人已经换到免费的[Mac zip](https://ezip.awehunt.com/)|是|$24.95|[官网](https://www.macitbetter.com/)|

*个人在使用Mac zip时，出现多次打开内有8000多张png图片的zip压缩包假死情况，已经反馈开发者，不过免费的要啥自行车……*

## 系统工具


像我一样的很多人，在从win到mac时，会感到很多操作的割裂感，因为这两套系统很多的操作逻辑是相反的，而且一些新增（比如win下没有的dock栏目）或者Mac下不同于win的软件安装逻辑，我们需要很多的“系统辅助”软件来让手头的工具更符合自己使用的直觉，毕竟电脑是给人服务的。不能买个爹回家吧？

以下的工具仅服务与我个人，而且算是这段时间再各个同质化非常严重的软件海洋中找到的好东西。

|类别|软件名称|一句话功能简介|是否原生支持M1|售价|安装来源|
|:-:|:-:|:-:|:-:|:-:|:-:|
|系统工具|超级右键|让你的右键像win下一样强大|是|18元/年&40元买断|[Mac App Store](https://apps.apple.com/cn/app/%E8%B6%85%E7%BA%A7%E5%8F%B3%E9%94%AE-irightmouse/id1497428978?mt=12)|
|系统工具|键指如飞|macOS快捷键查看|是|免费|[官网](https://www.better365.cn/FlyKey.html)|
|系统工具|Paste|专业的剪切板记录增强工具(最近在测试国人写的[PasteNow](https://apps.apple.com/cn/app/pastenow-%E5%89%AA%E8%B4%B4%E6%9D%BF%E5%B7%A5%E5%85%B7/id1552536109?mt=12))|是|13元/月|[Mac App Store](https://apps.apple.com/cn/app/paste-clipboard-manager/id967805235)|
|系统工具|Magnet Pro|窗口整理神器|是|50元|[Mac App Store](https://apps.apple.com/cn/app/magnet/id441258766?mt=12)|
|系统工具|小历|好用的第三方日历|是|ios1元，mac18元|[Mac App Store](https://apps.apple.com/cn/app/%E5%B0%8F%E5%8E%86-%E5%B0%8F%E8%80%8C%E7%BE%8E%E7%9A%84%E6%97%A5%E5%8E%86/id1114272557?mt=12)|
|系统工具|Pop Clip|划词扩展工具|否（可转译）|88元|[Mac App Store](https://apps.apple.com/cn/app/popclip/id445189367?mt=12)|
|系统工具|Yoink|一款移动复制文件效率工具|否（可转译）|50元|[Mac App Store](https://apps.apple.com/cn/app/yoink-%E6%8B%96%E6%94%BE%E4%B9%9F%E5%8F%AF%E4%BB%A5%E8%BD%BB%E6%9D%BE%E8%87%AA%E5%A6%82/id457622435?mt=12)|
|系统工具|iStat Menus|优秀的系统监控工具|是|US$11.99|[建议官网](https://bjango.com/mac/istatmenus/)|
|系统工具|Bartender 4|方便的管理菜单栏图标|是|US$15.00|[官网](https://www.macbartender.com/Bartender4/)|
|系统工具|One Switch|系统功能快速开关工具|是|30元|[官网/数码荔枝](https://store.lizhi.io/site/products/id/271?cid=mgeblp1f)|
|系统工具|Dock View|Dock栏应用窗口预览，就像Windows那样（doge）|否（可转译）|€16.99| [官网](https://noteifyapp.com/dockview/) |
