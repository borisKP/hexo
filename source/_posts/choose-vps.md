---
title: 什么是VPS？多种VPS类型又该怎么选？
date: 2019-08-04 15:54:50
tags:
- VPS
- 建站
categories:
- 折腾笔记
---
也许大多数人都有购买虚拟产品的经历，从我们经常交的电话费，到一个Q币，一个XX会员。这些都是看不见摸不到的虚拟产品。算起来VPS也是这类产品，不过也有些许的不同。


<!--more-->


VPS（Virtual Private Server）是一个虚拟服务器，也就是将一台服务器分割成多个虚拟专享服务器。你可以想象成你在北上广租不起一整套房，但至少可以租个单间吧？这个“单间”就是你的某一个“VPS”（简单粗暴的理解方式，请轻拍）。
当然了，一台好的，专业的服务器自行购买是很土豪的一件事情，首先你得有一个机房，一台7*24不断线的服务器专业主机，当然还得有一条专线联网才行。然而咱可不是每一个都能搞定这么多的“装备”；于是便出现了服务器出租商。可是出租的服务器非常昂贵，你不但需要购买一台你可能永远看不见的服务器，而且当服务器宕机或者硬件需要维修时，必须得有人在机器旁“服务”。这年头人力成本可是非常昂贵滴。况且你也不一定需要一台服务器所有性能~

![机房][1]

这时候，我们的VPS就登场了，聪明的J商们在这里会对你说：“来来来，咱这里有便宜的服务器哦，你可以拥有这台服务器的全部功能，而且价格也很便宜哦，巴拉巴拉~~~~~”
这里J商说的话基本是正确滴。**但是！但是你拿到手里的只是这台服务器很小的一部分！**无论是服务器的宽带，内存，硬盘，CPU，还是服务器的实际控制区域，我们都只有一部分可以用，而且有的部分可能与别人一起使用（按照上文理解成公共卫生间与厨房即可）。但是物美价廉！

![VPS][2]


----------
上文说了这么多，如果你也和我一样也想入坑，那么可能就要说了，买什么好呢？
（租单间也要看是不是周围有医院、超时、打车方不方便）
购买VPS时经常看到有很多不同的平台，像OPENVZ、KVM、Xen、VMware，近年来又有了云主机云VPS。对于初次接触VPS的人来说，如何挑选VPS平台成了一件令人头疼的事。正因为有这样的困惑，很多VPS商干脆不再提及VPS究竟使用了什么平台。但是仍然有很多的VPS商提供了多种不同的VPS平台供用户选择，价格不一配置不一。那么这些不同的VPS平台区别和共同点是什么呢？OPENVZ、KVM、Xen、VMware哪个平台更好呢？
其实简单说，VPS的平台可以分为2类，一类是KVM、Xen、VMware；另一类就是OPENVZ了
1.KVM、Xen、VMware这一类就像房地产开发商是个土豪。每一个房间里都有自己独立的卫生间，厨房，甚至车库，停机坪（额，扯远了）
优点是每个VPS直接都有充分的隔离，你受你的邻居影响最小。（楼上漏水和电梯停电之类的不算）[抠鼻]。
缺点自然是整体使用量少，有浪费！而且贵。（什么？为什么贵？自己看看租房的价格，同地段两居室和一居室价格几乎一样）
2.而OPENVZ这类呢，就像是咱们现在的商品房，两居室，三居室，之类的。
优点是利用率大，而且价格低廉（本人就是这种）
缺点是你受你的邻居影响很大，而且可能房东为了赚黑心钱，可能会把你们的客厅也隔出一间屋子让人住。甚至出现卖床位的现象（关于超卖一事，请看之后的文章，先挖坑）
3.关于云VPS有点想现在互联网+里头的廉租房，小米租房就是个典型例子。暂且不表。

从上面就可以得出，其实小居室（传统KVM、Xen、VMware）是今后的发展方向，但如果你RP大爆发，邻里和睦；OPENVZ也是一个不错的选择。就现阶段而言，因为OPENVZ价格低廉效率好速度快，OPENVZ仍是最受欢迎的低价VPS首选。

参考文章的原地址：[http://hostbus.net/forum.php?mod=viewthread&tid=156058][3]


  [1]: https://i.loli.net/2019/06/28/5d15d2e454c2151703.jpg
  [2]: https://i.loli.net/2019/06/28/5d15d350bc95135905.jpg
  [3]: http://hostbus.net/forum.php?mod=viewthread&tid=156058
