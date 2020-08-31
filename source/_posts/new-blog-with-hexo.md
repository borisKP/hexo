---
title: 用hexo搭建github博客详细全图解-转自简书
date: 2020-08-17 11:49:22
tags:
- 建站
categories:
- 折腾笔记
---
又是很久没有使用过hexo了，忽然想记录点什么，居然连hexo的搭建方式都逐渐忘记，还好有如下的文章可以参考。仅做备份，感谢原作者。

> 作者：从0到1的小姐姐
链接：https://www.jianshu.com/p/fde2cced630d
来源：简书
著作权归作者所有。仅为个人转载，侵删。

<!--more-->

如下正文：
----------

# 1.node.js下载安装 #
http://nodejs.cn/download/
建议：官网下载最新版本，如果不是最新版本后面可能会提示版本太低。
![1.jpg](https://i.loli.net/2020/08/17/ikD6rSf5VtGZq2h.png)
一路默认，默认安装在C盘，安装完成之后cmd中输入

	node -v

查看是否安装成功和相应版本
![2.jpg](https://i.loli.net/2020/08/17/MeIRmcs9PgGOKTN.png)

# 2.git下载安装 #
[https://git-scm.com/downloads](https://git-scm.com/downloads)

建议：官网下载最新版本，如果不是最新版本后面可能会报错
同上默认安装
![3.jpg](https://i.loli.net/2020/08/17/MgfR1Y3yXmDHCZw.png)

按照下图进行选择，将会使得Git安装程序在系统PATH中加入Git的相关路径，使得你可以在CMD界面下调用Git，不用打开Git Bash了。
![4.jpg](https://i.loli.net/2020/08/17/dB9hNir8ZxlIkUY.png)

检查一下Git是不是安装正确了，打开命令行，输入：


    git --version



![5.jpg](https://i.loli.net/2020/08/17/zUCOZWaAEpVfY8n.png)

# 3.github账户的注册和配置 #

- 注册很简单，就用户名+邮箱+密码，然后邮箱验证哈，注意的是给自己取一个方便记住的用户名！


- 配置：
- 
## 3.1创建代码库 ##

选择New repository
![6.jpg](https://i.loli.net/2020/08/17/M7diSBLD1aWNV5z.png)


在Repository name下填写yourname.github.io，Description (optional)下填写一些简单的描述（不写也没有关系），如图所示：

![7.jpg](https://i.loli.net/2020/08/17/v5C4K3Yema1NAdE.png)


## 3.2 代码库设置 ##
正确创建之后，你将会看到如下界面：

![8.jpg](https://i.loli.net/2020/08/17/FCTlajIdGs5JDEZ.png)

点击界面右侧的Settings，你将会打开这个库的setting页面，向下拖动，直到看见GitHub Pages，如图：
这里我们需要点击Choose a theme任意选择一个选择主题，然后界面会跳转到仓库，我们看到有两个文件如下：

![9.jpg](https://i.loli.net/2020/08/17/LzHrTbV1EwD2nOs.png)

![10.jpg](https://i.loli.net/2020/08/17/RZg1omB6vNA5a8t.png)

此时若再查看setting，我们会看到开启GitHub Pages之后得到的域名如下：

![11.jpg](https://i.loli.net/2020/08/17/53jYkHaw8PyteI4.png)

我们就可以使用`https://UserName.github.io`，访问自己的博客网站了

![12.jpg](https://i.loli.net/2020/08/17/RheDaJGSiKTEIAj.png)

# 4.安装和配置Hexo #
## 4.1安装 ##
在E盘或者其他盘的根目录下新建一个名为hexo的文件夹

![13.jpg](https://i.loli.net/2020/08/17/GlOc8rDCMN4hqb7.png)

右键单击，单击Git Bash Here,打开git命令窗口中输入以下命令：


    npm install hexo-cli -g


![14.jpg](https://i.loli.net/2020/08/17/gWeZKLiwNtds7nf.png)

至此出现第1个问题：

    npm WARN engine hexo-fs@0.2.3: wanted:{"node ":">=6.9.0"}(current:{"node":"4.2.3","npm":"2.14.7"})


提示node的版本不够，所以前面提示大家要安装比较新的版本！重新去官网下载然后安装！
![15.jpg](https://i.loli.net/2020/08/17/23akZc45jWen7Vu.png)

![16.jpg](https://i.loli.net/2020/08/17/KHgPc5RAVjLp7v9.png)

现在再来查看版本已经是v10.2.0

![17.jpg](https://i.loli.net/2020/08/17/PSM3wyuCRtAimZo.png)

然后再次


    npm install hexo-cli -g


![18.jpg](https://i.loli.net/2020/08/17/vaEPjFwqni3TIoM.png)

至此出现第2个问题：


    npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})


很多人也貌似出现了这个问题，参考了好几个帖子：
[https://segmentfault.com/q/1010000008223855](https://segmentfault.com/q/1010000008223855)
[https://www.imooc.com/qadetail/177063](https://www.imooc.com/qadetail/177063)
我参照改了源,也不确定这个是否有用

    npm config set registry https://registry.npm.taobao.org

然后输入

    npm install hexo --save

    hexo -v
然后看到如图，并不和其他帖子的hexo -v之后显示一样有hexo:版本，如果你的有这行，证明你安装对了，如果你的也没有，在接下来配置会尝试用一种方法解决！

![19.jpg](https://i.loli.net/2020/08/17/rWZTlYXwJIN6okM.png)

<center>或者</center>

![20.jpg](https://i.loli.net/2020/08/17/Gu2KxT6jsd4ZkSU.png)

## 4.2配置 ##
初始化`hexo init`
目录是刚刚创建的hexo目录下！即`/e/hexo`

![21.jpg](https://i.loli.net/2020/08/17/TslJ5bD9eYEGUCm.png)


再次查看，仍旧没有hexo:(如果你的有，请略过下面新建文件夹的步骤)

![22.jpg](https://i.loli.net/2020/08/17/iuJbjKyUkF7ehNs.png)

于是，在E盘重新建了一个文件夹HexoBlog,这个文件夹用来写后面需要发布的markdown文件，前面的hexo文件夹就当做安装目录吧！
切换到`cd /e/HexoBlog`

![23.jpg](https://i.loli.net/2020/08/17/CI9uqrJpPYiwlF2.png)

然后接下来
初始化`hexo init`

![24.jpg](https://i.loli.net/2020/08/17/Ookg5LM9mW2XAHy.png)

安装插件`npm install`
如果npm install不能完全安装好，就参照下面的图，一个个自己安装吧！
在此，引用一下一位仙女的笔记
[https://shirley5li.me/2017/08/06/hello-world/](https://shirley5li.me/2017/08/06/hello-world/)

![25.jpg](https://i.loli.net/2020/08/17/IgCp2cOeXzsvJP5.png)

提前安装好应有的插件！不然可能后面会报错！
生成`hexo g`

![26.jpg](https://i.loli.net/2020/08/17/7RU4h2VsEz81gWA.png)

运行server `hexo s`

如果正确的话将会看到如下提示信息

    INFO Hexo is running at [http://0.0.0.0:4000/](http://0.0.0.0:4000/). Press Ctrl+C to stop.

在浏览器中打开[http://localhost:4000/](http://localhost:4000/ "0")，你将会看到：

![27.jpg](https://i.loli.net/2020/08/17/RHIBqdatlEvgObk.png)

到目前为止，Hexo在本地的配置结束。

# 5.将Hexo与github page 联系起来 #
## 5.1配置git ##

继续在`/e/HexoBlog`目录下，输入


	git config –-global user.name “Tidy1993”  //(“”的账号是刚才Github里面自己注册的账号)   
	git config –-global user.email “354122535@qq.com” //(""的邮箱是你自己注册的邮箱)  


## 5.2配置和测试SSH ##
然后，切换到

    cd ~/.ssh
    ssh-keygen -t rsa -C “354122535@qq.com” //打自己的邮箱
  
按照下图，回车，然后输入自己登陆github的密码两次，直到生成图示

![28.jpg](https://i.loli.net/2020/08/17/bIjODAPFMxVurKo.png)

去到C盘找到.ssh文件夹，打开id rsa.pub文件，复制里面代码

![29.jpg](https://i.loli.net/2020/08/17/gH8IqN3j2mpdy6c.png)

![30.jpg](https://i.loli.net/2020/08/17/r2yd4FEYZnkPiac.png)

![31.jpg](https://i.loli.net/2020/08/17/W4wcSloCBzMPhA2.png)

![32.jpg](https://i.loli.net/2020/08/17/G81l65yZzJgKOfx.png)

把刚刚粘贴的密码粘贴到上面key中，点击`Add SSH key`
测试ssh设置是否成功

    ssh -T git@github.com

![33.jpg](https://i.loli.net/2020/08/17/SJBnuFx9ITp1q47.png)


## 5.3 配置Deployment ##
手动找到`/e/HexoBlog`目录下的`_config.yml`文件，然后右键点击，打开文件

在文件最后deploy：这里加上下面代码

	deploy:
	  type: git
	  repo: git@github.com:Tidy1993/Tidy1993.github.io.git
	  branch: master



我的用户名是Tidy1993上面的yourname改成你自己的

# 6.写第一篇博客，同步到github #
继续在`/e/HexoBlog目`录下输入

	hexo new post "article title"

![34.jpg](https://i.loli.net/2020/08/17/kHYTj9iD3MLVBZg.png)

然后在对应的目录下，会生成对应的.md后缀的文件

![35.jpg](https://i.loli.net/2020/08/17/tfgdsKCkOTyvSHQ.png)

我还没用markdown的编辑器，暂时用notepad打开文件，然后前面---之间的内容不能删，title就是一会儿显示在github上的title,后期可以改，然后在第二个---之后键入内容，要用markdown语法！完了之后保存！

![36.jpg](https://i.loli.net/2020/08/17/mHYW8GwCXvE4ONu.png)

回到git命令行中，输入

	hexo g   // 生成
	hexo s   // server

![37.jpg](https://i.loli.net/2020/08/17/SXl3E9gs2fLzeOM.png)

在浏览器输入：[localhost:4000](http://localhost:4000)在本地查看刚刚新建的md文件，在此可以看到已经在本地了

![38.jpg](https://i.loli.net/2020/08/17/NnIR9xq46Qw3TrM.png)

回到git命令行中，输入

	hexo d  // develop部署

![39.jpg](https://i.loli.net/2020/08/17/9zEbNUvnyGxLoli.png)



- 如果这里运行 hexo d之后出现错误

	ERROR Deployer not found: git

- 安装这个插件！

	npm install --save hexo-deployer-git

- 正确运行的话会提示输入github密码

![40.jpg](https://i.loli.net/2020/08/17/VG4N9PkE2QTWjMq.png)

正确之后会显示如下，表示成功同步到github帐号

![41.jpg](https://i.loli.net/2020/08/17/vrs4EAS3CLzQTaB.png)

在浏览器输入：`https://tidy1993.github.io`对应的github域名，就可以看到效果啦！

![42.jpg](https://i.loli.net/2020/08/17/UtfRFZhwiKOerHG.png)

至此，终于有自己的github帐号并且有博啦！开心！虽然过程挺痛苦的！
# 总结一下出现的问题： #
## 问题1： ##

	npm WARN engine hexo-fs@0.2.3: wanted:{"node ":">=6.9.0"}(current:{"node":"4.2.3","npm":"2.14.7"})

提示node的版本不够，所以前面提示大家要安装比较新的版本！重新去官网下载然后安装！

## 问题2： ##

	npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})

很多人也貌似出现了这个问题，参考了好几个帖子：
[https://segmentfault.com/q/1010000008223855](https://segmentfault.com/q/1010000008223855)
[https://www.imooc.com/qadetail/177063](https://www.imooc.com/qadetail/177063)

## 问题3： ##
如果输入`hexo -v`没能出现对应版本提示，新建个文件夹，记得在对应的目录下

	npm install hexo-cli -g
	npm install hexo --save
	hexo -v
	hexo init
	npm install
	hexo g
	hexo s
## 问题4： ##
配置完git,记得配置SSH，在ssh配置时输入的密码是你登录github的密码，不要自己又重新设一个密码！

## 问题5： ##
配置development的时候，在自己建立的hexo文件夹下面找_config.yml文件，因为我先后建立了两次文件夹，所以我就改了两次，讲道理，应该只有hexo一个文件夹，下面需要改

## 问题6： ##
新建一个博客，必须在命令行中取名字，不能写好.md文件放在目录下而不执行

	hexo new "article title"

完了之后必须

	hexo g

	hexo d

	hexo s

不是必须的，只是为了在同步上去github之前在本地浏览一下是否合适，如果觉得没问题，可以忽略这一步，直接g和d.


> 作者：从0到1的小姐姐
链接：https://www.jianshu.com/p/fde2cced630d
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
