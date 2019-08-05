---
title: 更换电脑后继续更新HEXO博客的办法
date: 2019-08-05 14:13:16
tags:
- HEXO
- 建站
categories:
- 折腾笔记
---
在新电脑上安装好最新的node.js与Git
在新机器上创建hexo文件夹
对文件夹右键启动Git
`git init` //建立主仓库
`git remote add origin git@github.com:yourusername/test.git` //连接仓库
`ssh -T git@github.com` //测试是否登录Github
`git pull origin master` //拉取Github数据

修改添加删除你的仓库数据后

`git add .` //把整个文件夹添加进缓存
`git commit -m "版本备注"` //添加版本备注信息，注意备注不能为空
`git push -u origin master` //推送新版至你的仓库

如果在操作hexo命令时（hexo s）之类的命令时，请务必提前执行如下命令：
`npm install hexo-server --save`
如果还是不行，请执行：
`npm install`
	