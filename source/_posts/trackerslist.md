---
title: BT种子获取更多连接的方案（增加trackerslist）
date: 2019-08-27 20:46:40
tags:
- 做种
- PT
categories:
- 关于PT的两三事
---
相信很多小伙伴都有如下的经历：
在TR或者UT之类的BT客户端上，打开了一个`.torrent`种子，下载非常缓慢，经常处于10KB/S到100KB/S的区间，有时候甚至没有速度，每次打开PC就挂着这个种子，时间久了，也许就没有了下载的动力…………
有的种子还好，全网努力搜索，还可能找到一些替代品；但有的种子，你无论如何都找不到可以替代的，又是那种非常古老的稀缺资源。这个时候你就需要**trackerslist**的出场了。
## trackerslist ##
**[trackerslist](https://github.com/ngosang/trackerslist)**是GitHub上，一位西班牙程序员*Diego Heras*制作的表单，这个list中含有现今世界上绝大多数的明文Trackers服务器链接地址。如果你的种子没有速度，可以尝试添加上这个表单中的Trackers，没准可以让你的种子活下去~

首先当然是需要看看**trackerslist**的[README.md](https://github.com/ngosang/trackerslist/blob/master/README.md)了，在这个README.md中*Diego Heras*给我们详细介绍了public BitTorrent trackers的种类与区分，下面是本人对此的中英文对照翻译。


----------

> # ngosang/trackerslist
> Updated list of public BitTorrent trackers
	
> 公共BT-tracker更新列表
> #### Updated: 2019-08-27
> *These lists are automatically updated every day:*
	
> 如下的表单每天都会自动更新
	
> * trackers_best (20 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_best.txt>
> * 最好的20个trackers
> * trackers_all (93 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all.txt>
> * 全部的93个trackers
> * trackers_all_udp (49 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all_udp.txt>
> * 全部的UDP-trackers，共计49个
> * trackers_all_http (34 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all_http.txt>
> * 全部的http-trackers，共计34个
> * trackers_all_https (10 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all_https.txt>
> * 全部的https-trackers，共计10个
> * trackers_all_ws (4 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all_ws.txt>
> * 全部的wws-trackers，共计4个
	
> Are you having DNS problems? These lists contains the same trackers but with IP addresses instead of domains:
> 如果你的DNS有一些问题（例如DNS污染等）你可以通过IP来链接上述表单中的trackers，而不是通过域名链接：
	
> * trackers_best_ip (20 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_best_ip.txt>
> * 最好的20个trackers
> * trackers_all_ip (80 trackers) => <https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all_ip.txt>
> * 全部的80个trackers
	
> ##### Notes
> * A bot automatically checks the trackers and updates the lists.
> * 系统机器人会自动查验全部trackers，并自动更新表单。
> * Trackers with the same domain or pointing to the same IP address are removed. Check out the [blacklist](https://raw.githubusercontent.com/ngosang/trackerslist/master/blacklist.txt).
> * 重复域名或者重复IP的表单将会被删除，详见：[黑名单](https://raw.githubusercontent.com/ngosang/trackerslist/master/blacklist.txt).
> * Trackers are sorted by popularity and latency (from best to worst).
> * Trackers表单的顺序是按照热度以及迟延情况排序（从好到坏）
> * WebSocket trackers (AKA WebTorrent, ws, wss) are supported by few clients. [More info](https://webtorrent.io).
> * 只有少数的客户端支持WebSocket trackers(AKA WebTorrent, ws, wss)，[点我查详细](https://webtorrent.io).
> * Lists with IP addresses can be shorter because [Cloudflare IPs](https://www.cloudflare.com/ips/) are removed.
> * IP地址的trackers表单比域名表单少，原因是我们在IP表单中删除了包含启用CDN的部分。[CDN列表](https://www.cloudflare.com/ips/)
	
> ##### Contribute
> * Do you know more public trackers? =[Open a new issue](https://github.com/ngosang/trackerslist/issues/new)
> * 如果你知道更多的公共trackers，欢迎告诉我
> * Any of the trackers is not working properly? =[Open a new issue](https://github.com/ngosang/trackerslist/issues/new)
> * 如果有不工作的trackers，欢迎告诉我
	
> ##### Contact
> ngosang [@] hotmail [.es]
	
> *原Po联络方式*
> ##### Donations
> 捐助信息：
	
> * [![Beerpay](https://beerpay.io/ngosang/trackerslist/badge.svg?style=flat)](https://beerpay.io/ngosang/trackerslist)
> * BTC: [1JMkeuLX9DA8sssZLSeSvSRvS1iVCu2wNT](https://btc.com/1jmkeulx9da8ssszlsesvsrvs1ivcu2wnt)
> * ETH: [0x50A79a95878dd588A55E909dAc2eA3962D2fA46c](https://etherscan.io/address/0x50A79a95878dd588A55E909dAc2eA3962D2fA46c)
	
> ##### Third-party tools
> 第三方工具
	
> * [bittorrent-tracker-editor](https://github.com/GerryFerdinandus/bittorrent-tracker-editor) to add these trackers to your .torrent files
> * [transmission python script](https://github.com/blind-oracle/transmission-trackers) to add these trackers to [transmission](https://github.com/transmission/transmission)
> * [transmission bash script 1](https://github.com/AndrewMarchukov/tracker-add) to add these trackers to [transmission](https://github.com/transmission/transmission)
> * [transmission bash script 2](https://github.com/oilervoss/transmission) to add these trackers to [transmission](https://github.com/transmission/transmission)
	
> ##### Third-party online tools
> 第三方在线工具
	
> * [torrenteditor](http://torrenteditor.com) to add these trackers to your .torrent files

----------

## 在Transmission中添加trackerslist ##

**以下方案均在Unix版本与Synology版本Transmission中的[transmission-web-control](https://github.com/ronggang/transmission-web-control) Web页面操作**

**Win版本、Mac OS版本未进行测试**

**原版Transmission的Web Client没有此项功能！**

**原版Transmission的Web Client长这样，[点击查看](https://transmissionbt.com/images/screenshots/Clutch-Large.jpg "https://transmissionbt.com/images/screenshots/Clutch-Large.jpg")**

在拿到你需要的trackerslist后就需要往你原来的种子中添加新trackers了，因为我用的比较多的是Transmission，这里教大家在Transmission中添加新trackers的方法：
首先打开你的Transmission，登陆一气呵成。
![](https://user-images.githubusercontent.com/8065899/38598199-0d2e684c-3d8e-11e8-8b21-3cd1f3c7580a.png)

然后根据如下图的顺序，找到你需要增加trackerslist的种子，点击选中，在下方的“服务器”中，找到如下图“标记3”的地方点击增加trackers

![](https://i.loli.net/2019/08/29/BshpDejJP8wlI2Y.png)

在弹出的框中，每行增加一个Tracker（也就是直接“复制”+“黏贴”）

![](https://i.loli.net/2019/08/29/EtSJka8DCLmMYgN.png)

增加完成后等一杯咖啡的时间，你新增加的所有Tracker就会自动刷新并连接上了~

![](https://i.loli.net/2019/08/29/1jXxsLkhMCBwHqD.png)

怎么样？试试速度吧~

![](https://i.loli.net/2019/08/29/J4bHoMGCRD3hIWZ.png)