---
title: 揭开PT的真实面纱–PT（Private Tracker）萌新到小白的过程
date: 2019-08-03 21:44:20
tags: 
- NAS 
- PT
categories: 
- 关于PT的两三事
---
[![](https://i.loli.net/2019/07/25/5d393ea07c69f18330.jpg)](https://i.loli.net/2019/07/25/5d393ea07c69f18330.jpg)
> PT（PrivateTracker）下载其实也是BT下载的一种，和BT下载有两个最明显的不同，即私密的小范围下载和进行流量统计。BT下载时，BT客户端首先解析.torrent种子文件得到Tracker地址，然后连接Tracker服务器。Tracker服务器回应下载者的请求，提供其他下载者（包括发布者）的IP。下载者再连接其他下载者，根据.torrent文件，两者分别向对方告知自己已经有的块（数据），然后交换对方没有的数据。此时不需要其他服务器参与，分散了单个线路上的数据流量，因此减轻了服务器负担。Tracker是BT下载的一个重要组成部分，用于记录上下载用户的互连信息。而PT下载和BT下载的区别是PT下载的Tracker是私有的，BT下载的Tracker则是公开的。 
PT下载是一种小范围的BT下载，通过禁用DHT，有要求地选择并控制用户数量。这样，在有限的范围内，下载的用户基本都可以达到自己带宽的上限。PT下载还通过论坛制度的约束机制将BT的设计理念现实化，真正让用户做到下载的过程中努力上传。因此，PT下载的速度很快，能够让用户带宽得到最大程度的使用，而且种子时效长。 

上面两段来自专业网站对PT的解释，如果你还想了解更多，请参考：[Wiki百科](https://zh.wikipedia.org/wiki/PT%E4%B8%8B%E8%BC%89 "Wiki百科")

<!--more-->

------------

怎么说呢？其实关于PT的出处已经无从查证了，不过这的确是在北美地区流行后，慢慢辐射到我国的，其实世界各地都存在着各式各样的PT社区；
我首次认识到PT其实也算是比较迟了，在2015年的时候，那个时候，初次接触到服务器，也深入了解了当时万恶的ADSL不对等拨号网络，同时也在刷路由器折腾“多拨”什么的（不过这就是另一个故事了……）
在当时，我去翻论坛的帖子，看到很多人都在说“多拨”后下载速度不叠加，但上传叠加；开始的时候我还不知道上传有什么用？（~~我可是当年迅雷的白金会员~~）直到帖子中出现了一句：“你上传叠加翻倍，用来刷PT岂不是太好？”
当时因为好奇就去搜索了下什么是PT，尼玛啊……以下子就进入了深坑！
其实PT在最开始的时候，解决了我的一个疑问：
##### *为什么正在下载的BT种子，上传速度越快，下载速度也同步越快？*
(请原谅我作为一个萌新的愚蠢)
因为当时的我一直都在租住房子，没有一个安定的小窝，也没有一台高清电视，这导致我对很多PT站点的高清资源没有特别的需求，网络也是一个问题。所以就放下了刷刷刷的事情。直到今年年初，家里的装修进入尾声，家里也拥有了人生第一台电视（索尼大法好）和第一台NAS（蜗牛矿渣真香），才又开始萌生玩PT的念头，因为我个人接触PT较早，原理啥的都略懂一些，在逛论坛以及电报的聊天组时，发现很多新接触PT的玩家，其目的和PT的本质是背道而驰的，都不太会玩，很容易被ban掉。我就结合自己在玩PT的过程中所产生的问题以及解决方案，算是写个备忘录给自己看，可能会有不严谨的地方。如果你也看到了本篇文字，也对你产生了帮助，我很高兴！
[![](https://i.loli.net/2019/07/26/5d3a891dbabe315809.jpg)](https://i.loli.net/2019/07/26/5d3a891dbabe315809.jpg)

------------

### PT下载是如何实现的？ ###
对于BT，许多人都有一个基础的认知，就是下载的人数越多，自然下载的速度也就越快。但是你别忘了，国内很多人在用迅雷这样的吸血工具，他在下载时并没有上传，而且下载完成后，就戛然而止，没有持续性的上传，而PT就不同了，PT是一个规则性极强的社区，这意味着您需要成为会员才能查看网站内容并下载其种子，新会员必须通过一定的努力得到内站邀请才可以加入，邀请注册机制有效地控制了下载人数。 
通常意义上，在各大PT站点，你的标准“货币”就是“上传量”，你需要下载50GB的资源，那么你就需要50GB的上传，在这样的大规则之下，大家都在努力的争先恐后的贡献自己的上传资源，自然下载的人速度就快。
### 在哪里可以找到这些社区站点？###
您可以通过一些综合性的论坛找到PT站点，因为PT站点大多都是一个小规模的私人性质很浓的圈子，基本上各大PT站点都不会被搜索引擎所收录。
比较热门的“四大”站点是：M-Team、CMCT、TTG、HDSky；您可以通过关键词查找到他们的登陆地址。
不过因为各大PT站点都实行邀请制，如果你周围没有一两个玩这个的朋友，或者恰逢某个PT站点开放注册（可能性很小）；募捐入站也是一个不错的选择。
很多站点界面上都会有“捐赠”按钮，一般捐赠之后就可以获得一定时间内的VIP待遇，时间过了之后就相当于一个普通账号了，当然如果捐的比较多，可能是永久VIP，（土豪，请！）对于更多的人来说，获得要求的方法就是在一些平台上面求邀请码，比如百度贴吧（PT吧）、一些人流量比较大的论坛、交流群等。具体的就因人而异了，不一一赘述。
[![](https://i.loli.net/2019/07/26/5d3ad3dcd4e9e43090.png)](https://i.loli.net/2019/07/26/5d3ad3dcd4e9e43090.png)
### 软件 ###
PT站点的流通文件时规范的.torrent种子，正如本篇一开头所述，PT也同样使用BT下载中使用的客户端软件，不过考虑到各种“定制化”的软件（例如只下载不上传的迅雷），各个PT站点都会在“常见问题”中注明可以使用的软件类型，如下图，这里不做太多的赘述；
仅仅告诉你我的建议：
win系统：建议使用[uTorrent](https://www.utorrent.com/ "uTorrent")
linux系统：建议使用[qbittorrent](https://www.qbittorrent.org/ "qbittorrent")与[Transmission](https://transmissionbt.com/ "transmission")
MacOS系统：建议使用[Transmission](https://transmissionbt.com/ "transmission")
Android系统：建议使用[Transmission Remote](https://play.google.com/store/apps/details?id=net.yupol.transmissionremote.app "transmission remote")
IOS系统：不知道鸭~
![blob.jpg](https://i.loli.net/2019/07/27/5d3c731e600de83289.jpg)
### 考核期 ###
如果你看了如上的文字，你肯定会知道，PT站点的主要目的就是“上传量”了。而且准入机制是“邀请制”，这里的门槛已经过滤掉了一部分的人；然而，这还不够，各大PT站点还出现了：“新手考核”制度，最寻常的新手考核制度主要有如下四个方面：

1）上传量  //主要是看你上传了多少数据，一般会在30GB-50GB不等；
2）下载量  //需要下载数据，主要是统计“分享率”而设定的中间量；
3）分享率  //上传量除以下载量就是分享率，正常情况下需要分享率大于1；
4）魔力值  //因为PT的主旨就是分析，你分享的种子数量越多，魔力值就越多，如果你有较好的资源可以发布，那更加会帮助你的魔力值提升；

通常情况下，各大PT站点用新手考核的方式来过滤掉绝大多数可以得到“邀请”的“吸血鬼”；这里的“吸血鬼”就很生动形象了，表示只下载不上传，不做种的那群人。如何通过考核期，这是一个摆在每位PTer面前的“考试”。如果通过了，恰巧你进入的PT站点又没有“增量考核”，那么，逐渐缓步的提升(俗称养号)你的账户等级就是你接下来该做的事情了。
> 发现很多新接触PT的玩家，其目的和PT的本质是背道而驰的!

这是我在本文一开头就说过的话，其实一个新手PTer想通过考核期，最重要的就是这个“**目的**”二字。如果你仅仅是为了某一部高清资源，或者你仅仅为了下载，不准备也没有任何的分享计划（设备，时间）的话；那么第一个被ban的人可能就是你，在考核制度里面，容易达成的下载率先不谈，其余几个我逐一介绍：
#### 上传量 ####
PT是基于BT的一种类型，完成上传量的考核方法方法有二：
1）你有稀缺资源，或者有本PT站点没有的资源，发布他就可以获得上传量！
**作为一个资源的发布者，你可以获得两倍的上传量。**
2）新手一般情况下，建议下载“FREE”的热门资源，你可以通过每个资源查看，去找那些上传人数少，下载人数多的种子，下载并默默做种上传吧！
这里要注意的是：
**你下载的东西，你做种上传的东西，可能并不是你需要的东西，你的目的是完成考核，而不应该在意这些数据的内容是否对你有用！！**
#### 魔力值 ####
对于魔力值，点击你主页上“魔力值”旁边的使用按钮，则可以进入“魔力值”页面，每个PT站点都会对魔力值做一个公式计算，如果明白了公式，自然可以向着需求所努力；但如果你看不懂公式，也没关系。其实魔力值不管是何种公式，其都是一种按照做种数量、做种时间和同一资源的做种人数做的计算。
简单而言，**你做种的资源越大，数量越多，资源珍惜度越高（做种人数少）**，那么每小时得到的魔力值就越多。
（下图是BTSCHOOL的魔力计算公式，供参考）
![BTSCHOOL bonus.jpg](https://i.loli.net/2019/07/26/5d3a764c0580536403.jpg)
#### 分享率 ####
分享率其实是一个大坑，如果没有仔细研读过各大PT站点的规则的话，很多人都会被ban在“分享率过低”上。
因为分享率是考验一个账号的上传/下载的动态平衡，新手可能会不注意，在某个时间段让自己的分享率将至零点几的样子。这时候就会收到一个系统短信：**如果十天内不改变分享率，账号就会被禁用。**，同时你的分享率过低也会让你本来可以同步下载无限多的种子，同时只能下载几个种子……
当当当当……这就是隐形的考核，各个站点都有明确的描述。
(这里我也用BTSCHOOL的规则来说明，以确保全文统一)
分享率低下会导致你进入“Peasant”用户等级：
 >Peasant	 	被降级的用户，他们有10天时间来提升分享率，否则他们会被踢。不能发表趣味盒内容；不能申请友情链接；不能上传字幕。
Peasant	 	当以下情况时将被自动降至本级：
1.如果你已经下载了超过50GB，你应该有大于0.4的分享率。
2.如果你已经下载了超过100GB，你应该有大于0.5的分享率。
3.如果你已经下载了超过200GB，你应该有大于0.6的分享率。
4.如果你已经下载了超过400GB，你应该有大于0.7的分享率。
5.如果你已经下载了超过800GB，你应该有大于0.8的分享率。

当你进入“Peasant”用户等级后的连接数限制：
> 这是“最大连接数系统”。最大连接数系统用于限制那些分享率较低且下载量大于10GB的用户的最大同时下载数。
规则如下: 
分享率低于	0.5	 	最大连接数	1
分享率低于	0.65	 	最大连接数	2
分享率低于	0.8	 	最大连接数	3
分享率低于	0.95	 	最大连接数	4
分享率大于	0.95	 	最大连接数	无限制
无论何时，同时的上传数不设限。但是如果你当前的下载数已达到了你的最大连接数，这时开启新的做种任务，你也会收到同样的错误提示。在这种情况下，你必须先关闭一个下载任务，然后开启所有的上传任务，然后继续刚才关闭的下载任务。因为当你的连接数被占满，系统将不加验证直接拒绝任何下载或上传的请求。 
你可以在任意时间察看自己的连接数，该信息在页面顶端信息栏中被列出。 

如果你认真读了上述的引用文字，你就会知道，你的只有当你的分享率大于1的时候，你才可以愉快的在PT社区内玩耍。各个不同的PT社区，其实规则都是大同小异的，那么要怎么过考核期呢？这里我总结了几点内容：
1）一个可以7 * 24运行并联网传输的机器，无论是NAS还是PC或者是路由器。
2）网络连接最好是有公网IP地址，如果有IPv6就更香了……
3）下载的资源不一定是你需要的，但一定得是热门资源！

### PT下载的优点： ###

为什么PT比BT下载快，其实它们的工作原理一样，都是从相互做种的人儿那儿得到自己想要的东西，但BT用户是公开不受约束的，往往一下载完就立马撤人的人比比皆是，人走茶凉，本来应该可以供的种子就没有了，因此，很多BT用户在下载时老嘀咕热门资源没种子，就是共享机制不够完善；而PT就不同了，用户在论坛上进行PT下载时，都有相应的约束机制。约束机制，才是下载速度有保证的根本。PT网站的约束机制是建立在分享率（radio）的基础上的。当上传量与下载量的比值达不到要求时，甚至会被ban帐号。也就是说，上传越多才能下载越多。因此，不少用户登陆PT软件不是为了下载，而是为了上传。不仅仅是速度上，种子的时效性也非常好，很多用户会主动保种。和公开的BT站点相比，靠制度远比靠自觉好。因此如果你幸运地进入内站，请记住一定要上传，否则你就会ban账号！
**这世界没有不劳而获的事情。**
[![](https://i.loli.net/2019/07/26/5d3ad3b5e61ad72918.jpg)](https://i.loli.net/2019/07/26/5d3ad3b5e61ad72918.jpg)
### PT下载的缺点： ###
#### 1.高高竖起的门槛：
现在的普通家庭，如果你也想享受PT带来的极致快速与高清的下载体验，那么你至少需要一块2T以上的大硬盘，外加一台NAS（或者类似NAS的不断电设备），这些都是需要真金白银花钱购买的。
隐形的宽带与电费我还没有算入。
另外玩PT就需要生存，生存下去就需要动脑筋，如果仅仅是希望无脑下载的话，这里也不是你的栖息地。
更重要的是时间，无论是PT魔力值的计算，电影原盘在电视机上的播放都需要你有足够的时间去研究。
#### 2.Tracker的脆弱性：
PT站往往只用自己的Tracker，和Public Tracker不同，PT的Tracker是要不停追踪客户端的下载上传流量的，所以对服务器的性能要求很高。Tracker服务器容易被攻破，导致用户 数据passkey泄露引起Tracker失效，就会无法统计上传下载流量，也就是常说的“红种”（种子文件显示为红色）问题。很多大水管也许无所谓，不过对于很多兢兢业业、如履簿冰正在努力上传的小水管用户来说，出现“红种”会让人有一种想去撞墙的冲动。
#### 3.The Pirate Bay
众所周知，现在网络上到处都是关于“正版”的言论，而“共享资源”这件事一直是被人垢病。您可以看看最新的[海盗湾Wiki](https://zh.wikipedia.org/wiki/%E6%B5%B7%E7%9B%9C%E7%81%A3 "海盗湾Wiki")，以及我之前缩写的那篇文章：“再见或再也不见—记readfree的告别”都在说明这个圈子的不断压缩，而且经常都会有一个新手，获得邀请后努力完成新手任务，最终还是因为一个不注意导致ban号。这样也会非常打击新手的自信心。你只是游戏者，人在你家的地盘就要遵守人家的规矩，而PT的规矩又是异常的多；
另外，这几年，开开关关了许多的PT站点，某天你所辛苦维护的PT站点也可能不在了，你会伤心吗……

“与其这样，为何我不去多花一杯奶茶的钱去冲一个视频网站的会员？”
如果你读到这里后，还会出现这样的想法，那么PT也许真的不适合你……

努力+幸运 
才是最终获得极致家庭视觉影音体验的唯一道路.






[![](https://i.loli.net/2019/07/26/5d3ad3eaf225b84214.png)](https://i.loli.net/2019/07/26/5d3ad3eaf225b84214.png)


