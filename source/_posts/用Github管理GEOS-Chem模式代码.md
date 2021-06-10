---
title: 用Github管理GEOS-Chem模式代码
tags: Tools
date: 2020-05-08 12:51:02
---


随着使用模式不断深入，经常需要修改模式代码。但是又担心修改过多导致混乱。所以今天下决心学习一下用Github管理项目代码。我参考了廖雪峰的教程和一些博客，感谢他们的奉献。

目前我仅学习了如何在本地项目建立分支（branch），如何注释自己的修改，并将修改后的版本推送到Github仓库里。未来学习了更多实用方法，我会更新这篇文章。下面我介绍一下操作方法。

# 创建远程仓库

首先在Github上创建一个空的仓库。创建完后，为了避免push的时候出现冲突，我删除了其中所有的东西。（PS 如果不想代码对外公开，创建仓库的时候可以选择Private resposity，这样别人就看不见了。现在创建私人仓库已经免费了，感谢微软。）

# 推送本地项目到远程仓库

然后进入本地项目的根目录，在我这里是GEOS-Chem模式的Code Directory。因为GEOS-Chem原本就是用Github托管的，本地的模式已经连接了官方的仓库，我要取消和官方仓库的连接，并和我自己的仓库连接。首先删除和官方远程仓库origin的连接：

```shell
$ git remote rm origin
```
然后建立和我的Github仓库`Holton1/GEOS-Chem-12.5.0`的连接：
```shell
$ git remote add origin https://github.com/Holton1/GEOS-Chem-12.5.0.git
```
然后推送到我的Github仓库里：
```shell
$ git push -f origin master
```

现在可以看见远程仓库里已经有模式代码了。但是检查了一下发现，我之前没有使用Github时已经做了一些修改，这些修改并没有被推送上去。推送上去的就是我最开始下载的原始版本模式。因为我推送的是模式的master branch，而我的修改并没有加入master branch。

# 创建新分支，注释并推送本地修改

下面创建一个新的branch，我的修改都在这个branch上。还是在本地模式根目录，用下面的命令创建新的branch，名字叫mywork：

```shell
$ git checkout -b mywork
```

检查目前在什么branch上：
```shell
$ git branch
```
发现我现在已经在mywork branch了。下面我给以前做的工作加注释，并把新的branch推送到远程仓库：
```shell
$ git add . 
$ git commit -m "My previous work"
$ git push origin mywork
```
现在到Github仓库，把branch改成mywork，检查代码。我看到了我之前做的修改！

# 总结

Github管理版本非常方便。以后学到了新技巧会更新本文。