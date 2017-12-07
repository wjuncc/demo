---
layout: post
title:  "ubuntu提交git"
date:   2017-12-06 21:17:32 +0800
categories:  
tags: 
---

# ubuntu提交git #

## 安装

	sudo apt-get install git

设置用户名和邮箱地址：

	git config --global user.name "XXX"
	git config --global user.email "XXX"

解释：
	
	git config --global user.name "YOUR NAME"
	git config --global user.email "YOUR EMAIL ADDRESS"


## 


从远程仓库下载文件

先cd到路径，再调用clone

	cd '/home/wj/blog'
	git clone https://github.com/wjuncc/demo.git
	git checkout gh-pages
	git pull origin gh-pages
	
	git push origin master


	git remote add origin https://github.com/dumengnanbuaa/learngit.git


上传到git

ubuntu写bash 上传git：

	#!/bin/bash
	git checkout gh-pages
	git pull origin gh-pages
	git add *
	git commit -m "update"
	git push origin gh-pages

直接双击无法执行。

	执行
	sudo：/home/wj/blog/upload_git.sh: command not found
	wj@wj-System-Product-Name:~/blog$ sudo ./upload_git.sh
	sudo：./upload_git.sh: command not found
	wj@wj-System-Product-Name:~/blog$ ./upload_git.sh
	bash: ./upload_git.sh: 权限不够
	wj@wj-System-Product-Name:~/blog$ 

# 在命令行执行

执行：
	
	./upload_git.sh

报错：

	bash: ./upload_git.sh: 没有那个文件或目录

换绝对路径：

	/home/wj/blog/upload_git.sh

报错：
	bash: /home/wj/upload_git.sh: 没有那个文件或目录


但是ls看又有这个文件,很是奇

bash: ./upload_git.sh: 权限不够
 linux下权限不够 chmod +x 脚本命令 ./脚本命令 
就是要写2行：

 	chmod +x ./upload_git.sh
 	./upload_git.sh


估计你是在Windows下编辑的，文件每行末尾会多出^M，所以建议先转格式：
搜索

	sudo apt-get install dos2unix

	dos2unix upload_git.sh

	dos2unix ~/blog/demo/upload_git.sh
	
#### 参考 ####

* [Ubuntu下Git的安装与使用_Linux教程_Linux公社-Linux系统门户网站](http://www.linuxidc.com/Linux/2016-09/135527.htm)
* [git和github在ubuntu上的使用 - CSDN博客](http://blog.csdn.net/u012526120/article/details/49401871)
* [Git与Github的使用(ubuntu)  PureWeber – 纯粹互联网](https://www.pureweber.com/article/git-and-github/)
* [Ubuntu下GitHub的使用 - Pythoner](http://www.pythoner.com/263.html)
* [Linux下的GitHub安装与简单配置教程 - 公子乱於世 - 博客园](http://www.cnblogs.com/smilejinge/p/3589479.html)
* [git与github在ubuntu下的使用 - Cocowool - 博客园](http://www.cnblogs.com/cocowool/archive/2010/10/19/1855616.html)
* [在Ubuntu上安装和使用Git和GitHub：初学者指南](https://www.howtoing.com/install-git-and-github-on-ubuntu-14.04)
* [Ubuntu下Git安装与使用-Bohsu-51CTO博客](http://blog.51cto.com/bohsu/1230705)
* [安装Git - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)
* [Git Manual](https://gist.github.com/bigeagle/3953973)
* [Ubuntu Git安装与使用_Linux教程_Linux公社-Linux系统门户网站](http://www.linuxidc.com/Linux/2016-11/136769.htm)
* [Ubuntu Git安装与使用 - CSDN博客](http://blog.csdn.net/yhl_leo/article/details/50760140)
* [如何在ubuntu下使用Github？ - CSDN博客](http://blog.csdn.net/tina_ttl/article/details/51326684)
* [ubuntu 14.04 使用git 和 github - CSDN博客](http://blog.csdn.net/small_rice_/article/details/44984027)
* [SmartGit 简明使用教程 – 克里斯的小屋](http://blog.chriscabin.com/others/git/1357.html)
* [Ubuntu下Git与Github的安装使用_Linux教程 - 帮客之家](http://www.bkjia.com/Linuxjc/1042977.html)