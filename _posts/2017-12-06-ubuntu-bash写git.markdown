---
layout: post
title:  "ubuntu bash写git"
date:   2017-12-06 21:17:32 +0800
categories:  
tags: 
---

## win系统要安装shell解释器 ##
为了同时能用grep, awk, curl等工具，最好装一个cygwin或者mingw来模拟linux环境。

cygwin
mingw

## shell不适合什么 ##
它的函数只能返回字串，无法返回数组  
它不支持面向对象，你无法实现一些优雅的设计模式  
它是解释型的，一边解释一边执行，连PHP那种预编译都不是，如果你的脚本包含错误(例如调用了不存在的函 数)，只要没执行到这一行，就不会报错

## shell的扩展名 ##
扩展名为sh（sh代表shell）
	
	chmod +x test.sh
	./test.sh

注意，写成./test.sh和写成test.sh不一样。  
win下的powerShell也是一个道理。  

	#!/bin/bash
	#!/usr/bin/php

“#!”是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行。


### 定义变量 ###
	var_name="value"

变量名和等号之间不能有空格。  
重定义变量，也是这么写。

下面这种不清楚

	for file in `ls /etc`
### 使用变量 ###

定义过的变量，加美元符号

	your_name="qinjx"
	echo $your_name
	echo ${your_name}

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：

	for skill in Ada Coffe Action Java; do
		echo "I am good at ${skill}Script"
	done

如果不给skill变量加花括号，写成echo "I am good at $skillScript"，

### 注释以“#”开头 ###
### 多行注释，每一行加一个#号 ###

代码用一对花括号括起来，定义成函数，没有地方调用这个函数，等于多行注释，   

### 字符串 ###
单双引号的区别跟PHP类似。

### 单引号 ###
单引号字符原样输出，定义变量无效  
单引号中不能出现单引号（用转义也不行）

	str='this is a string'


### 双引号 ###

双引号里可以有变量  
双引号里可以出现转义字符

	your_name='qinjx'
	str="Hello, I know your are \"$your_name\"! \n"



# ubuntu bash写git #
	
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

* [30min_guides/shell.md at master · qinjx/30min_guides · GitHub](https://github.com/qinjx/30min_guides/blob/master/shell.md)
* [shell执行git命令 - 简书](http://www.jianshu.com/p/bf7206fba067)
* [How to install git bash on ubuntu? - Stack Overflow](https://stackoverflow.com/questions/11491880/how-to-install-git-bash-on-ubuntu)