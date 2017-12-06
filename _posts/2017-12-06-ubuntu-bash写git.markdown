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

### 拼接字符串 ###

	your_name="qinjx"
	greeting="hello, "$your_name" !"
	greeting_1="hello, ${your_name} !"

	echo $greeting $greeting_1


### 获取字符串长度： ###

	string="abcd"
	echo ${#string} #输出：4

### 提取子字符串 ###

	string="alibaba is a great company"
	echo ${string:1:4} #输出：liba
### 查找子字符串 ###

	string="alibaba is a great company"
echo `expr index "$string" is`#输出：3，这个语句的意思是：找出字母i在这名话中的位置，要在linux下运行，mac下会报错

### 流程控制不可为空 ###

	if (isset($_GET["q"])) {
		search(q);
	}
	else {
		//do nothing
	}

举例：

### if ###
	if condition
	then
		command1 
		command2
		...
		commandN 
	fi
写成一行（适用于终端命令提示符）：

	if `ps -ef | grep ssh`;  then echo hello; fi
fi就是if倒过来拼写

### 	if else ###
	
	if condition
	then
		command1 
		command2
		...
		commandN
	else
		command
	fi

### if else-if else ###

	if condition1
	then
		command1
	elif condition2
		command2
	else
		commandN
	fi

### for循环 ###
for var in item1 item2 ... itemN
do
	command1
	command2
	...
	commandN
	done

写成一行：

	for var in item1 item2 ... itemN; do command1; command2… done;

### C风格的for ###

	for (( EXP1; EXP2; EXP3 ))
	do
		command1
		command2
		command3
	done


### while ###

	while condition
	do
		command
	done


### 无限循环 ###

	while :
	do
		command
	done
或者

	while true
	do
		command
	done

或者

	for (( ; ; ))

until

	until condition
	do
		command
	done



### case ###

case "${opt}" in
	"Install-Puppet-Server" )
		install_master $1
		exit
	;;

	"Install-Puppet-Client" )
		install_client $1
		exit
	;;

	"Config-Puppet-Server" )
		config_puppet_master
		exit
	;;

	"Config-Puppet-Client" )
		config_puppet_client
		exit
	;;

	"Exit" )
		exit
	;;

	* ) echo "Bad option, please choose again"
esac

case的语法和C family语言差别很大，它需要一个esac（就是case反过来）作为结束标记，每个case分支用右圆括号，用两个分号表示break

### 文件包含 ###

可以使用source和.关键字，如：

	source ./function.sh
	. ./function.sh

包含一个文件和执行一个文件一样，也要写这个文件的路径，不能光写文件名，比如上述例子中:

	. ./function.sh
不可以写作：

	. function.sh


real_path=`readlink -f $1`#$1是用户输入的参数，如function.sh

	. $real_path





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

* [Advanced Bash-Scripting Guide](http://tldp.org/LDP/abs/html/)
* [Shell脚本编程30分钟入门](https://github.com/qinjx/30min_guides/blob/master/shell.md)
* [30min_guides/shell.md at master · qinjx/30min_guides · GitHub](https://github.com/qinjx/30min_guides/blob/master/shell.md)
* [shell执行git命令 - 简书](http://www.jianshu.com/p/bf7206fba067)
* [How to install git bash on ubuntu? - Stack Overflow](https://stackoverflow.com/questions/11491880/how-to-install-git-bash-on-ubuntu)