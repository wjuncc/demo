---
layout: post
title:  "ubuntu bash写git"
date:   2017-12-06 21:17:32 +0800
categories:  
tags: 
    - ubuntu 
    - bash  
    - git 
---

ubuntu提交git 避免反复输入用户名密码
ubuntu push git 避免反复输入用户名密码



### 下面做法没有效果： ###

ubuntu当前用户目录

1. cd 回车;进入当前用户目录下;  
	输入：

		cd /home/wj
	
		vim .git-credentials

	 (如果没有安装vim 用其它编辑器也可以或 sudo apt-get install vim 安装一个)

3. 按照以下格式输入内容：

		

		https://{username}:{password}@wjuncc.github.com
　　
	其中username，password，github.com 都换成你自己的内容

4. 保存退出后执行下面命令

		git config --global credential.helper store

　　执行完后

		/home/用户名/.gitconfig 会新增一项

		helper = store

　　这是再执行git push/pull的时候就不会在要求你输入密码了。

# ubuntu bash写git #

	#!/bin/bash
	cd demo
	git checkout gh-pages
	git pull origin gh-pages
	git add *
	git commit -m "update"
	git push origin gh-pages

chmod +x  是什么？

	chmod +x upload_git.sh
	./upload_git.sh

shell执行git命令

	#! /bin/bash
	# 保存当前目录
	currentDir=$PWD
	echo "Start to publish...\n"
	# 切换到项目目录
	cd /usr/local/nginx/html/blog
	# 执行git命令
	git pull origin test
	git push origin master
	# 切换回原来的目录
	cd $currentDir
	# 删除缓存 
	rm -rvf /usr/local/nginx/html/blog/runtime/cache
	echo "Success\n";



#### 参考 ####

* [shell执行git命令 - 简书](http://www.jianshu.com/p/bf7206fba067)
* [How to install git bash on ubuntu? - Stack Overflow](https://stackoverflow.com/questions/11491880/how-to-install-git-bash-on-ubuntu)
* [windows--git bash中避免在push时反复输入用户名和密码](https://www.cnblogs.com/liuyuxiao/p/4907658.html)