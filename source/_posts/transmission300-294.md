---
title: 群晖套件的离线安装与降级--含Transmission3.0降级至Transmission2.94
date: 2020-10-09 15:13:55
tags:
- 服务器
- 群晖
categories:
- 折腾笔记
---

2020-08-02以来Transmission就推出了最新的3.0版本，作为Transmission的忠实用户，我也在第一时间体验了下，整体体验流畅，与2.94无区别。

查回官方文档，发现最大的升级改动便是：
**种子和 resume 文件名都会变成 40位 hash 值。**

对于我们这些通常需要挂PT的人来说。40位的hash值需要站点支持才可以，否则就全部“红种”。

对于至少10T以上的PTer来说全部重新校验简直就是晴空霹雳。

所以强烈建议暂时（至少在2020年底之前）都不要升级到Transmission3.0 ，继续使用2.94吧~

![transmission-tat2.jpg](https://i.loli.net/2020/10/09/hskFuWJiaBcDTIw.jpg)

<!--more-->

# 1. 在群晖上安装Transmission #

在群晖中安装Transmission套件的方法在网络上有大把教程，本次不再制造车轮，仅提供流程，具体方案建议大家自行搜索。

流程：
  套件中心--设置--常规--信任层级--“任何发行者”

  套件中心--设置--套件来源--新增源--`https://packages.synocommunity.com/`

# 2. 在群晖上“手动安装”套件（或降级） #

##   2.1基础流程： ##

  套件中心--手动安装--选择你所下载的`*.spk`文件

![Snipaste_2020-10-09_14-30-51.png](https://i.loli.net/2020/10/09/P86ApczNRuDVTqK.png)

 ##  2.2Synocommunity上的套件选择。 ##

登陆[Synocommunity](https://synocommunity.com/)官方主页。点击`Packages`进入套件列表。

![Snipaste_2020-10-09_14-41-15.png](https://i.loli.net/2020/10/09/abrqh4Qd3Xl6nAz.png)

下拉找到由Synocommunity提供的Transmission套件，点击进入

![Snipaste_2020-10-09_14-43-02.png](https://i.loli.net/2020/10/09/vnk7HUGNeP8biWT.png)

进入后可以看到有3.0版本也可以看到我们熟悉的2.94/2.93等版本，找到需要对应您群晖机器的版本下载即可。


![Snipaste_2020-10-09_14-46-20.png](https://i.loli.net/2020/10/09/nmwhbU7ArVBiQ3J.png)


关于群晖对应版本，可以查下群晖各类机型的套件架构：

[群晖官网点击查看](https://www.synology.com/zh-cn/knowledgebase/DSM/tutorial/Compatibility_Peripherals/What_kind_of_CPU_does_my_NAS_have)

> 此链接为群晖官网，进入后可以查看“套件架构”列，找到与您机器相对应的套件架构。

![Snipaste_2020-10-09_14-46-35.png](https://i.loli.net/2020/10/09/XdIEfS1OCJg5ply.png)

总结下黑群晖出没的机型架构:

|机型|套件架构|
|:-:|:-:|
|DS918+|Apollolake|
|DS3617xs|Broadwell|
|DS3615xs|Broadwell|

> 经过本人实测，如果您在X86机型上安装的黑群晖，则X86与X86_64两种架构也是支持的。
> 
> 架构前方的版本号均为最低版本，向上兼容，比如您的DSM是6.2.2,可以安装`5.0 x86_64`的`Transmission2.94-16`


# 3. 群晖中Transmission降级的风险 #

如果您的Transmission中已经做种超过10T或者还有正在下载中的部分。本次不建议降级。
如果非要降级，强烈建议您备份下Transmission 配置文件目录：

```
/volume1/@appstore/transmission/var/
```

最后，别忘记配置正确的权限与端口哟~

以上。



