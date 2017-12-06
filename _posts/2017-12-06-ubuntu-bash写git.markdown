---
layout: post
title:  "ubuntu bash写git"
date:   2017-12-06 21:17:32 +0800
categories:  
tags: 
---


# ubuntu bash写git #

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