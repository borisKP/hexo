---
title: git上传代码失败，报警正在向当前仓库加载另一个远程仓库的解决办法
date: 2020-09-07 13:54:45
tags:
- HEXO
- 建站
categories:
- 折腾笔记
---


接上文，[更换电脑后继续更新HEXO博客的办法](https://boriskp.github.io/new-PC-hexo/) 

<!--more-->

在我们更换电脑后，有时候从github上pull仓库代码时，会发现pull到一个空文件夹，当初我百思不得其解。

待从原始机器上重新`git add .`的时候，发现git报出如下错误代码。


```git
$ git add .
warning: adding embedded git repository: themes/next-reloaded
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint:
hint:   git submodule add <url> themes/next-reloaded
hint:
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint:
hint:   git rm --cached themes/next-reloaded
hint:
hint: See "git help submodule" for more information.
```

通过给出的告知，尝试`git rm --cached themes/next-reloaded`后还是不行，此条命令直接将待上传代码全部删除，而非解决无法上传。

再之后通过命令`ls -a`发现在本地`themes/next-reloaded`文件夹中有.git隐藏文件夹，分析可能是由于更新next主题时，使用`git clone`命令直接下拉导致。
随即删除本地`themes/next-reloaded`文件夹中的.git隐藏文件夹。

重新`git add .`即可成功上传，不再有报警提示。
