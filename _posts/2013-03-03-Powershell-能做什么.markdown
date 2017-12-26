---
layout: post
title:  "Powershell 能做什么"
date:   2013-03-03 14:01:12 +0800
categories: jekyll update
cats: 
    - powershell

---


# Powershell 能做什么 #
 
## Powershell 类似软件 ##
* [ConEmu](https://github.com/Maximus5/ConEmu)
* [Cmder](https://github.com/cmderdev/cmder)
* [sharex](https://getsharex.com)

## Powershell 基础 ##
Powershell 文件后缀名 .ps1  



入门教程

powershell有四版本，分别为1.0，2.0，3.0 ,4.0

* 如果您的系统是window7或者Windows Server 2008，那么PowerShell 2.0已经内置了，可以升级为3.0，4.0。
* 如果您的系统是Windows 8 或者Windows server 2012，那么PowerShell 3.0已经内置了，可以升级为4.0。
* 如果您的系统为Windows 8.1或者Windows server 2012 R2，那默认已经是4.0了。

### 通过netstat查看网络端口状态 ###

	netstat

### 通过IPConfig查看自己的网络配置 ###

	IPConfig

### route print查看路由信息 ###

	route print

### 启动CMD控制台 ###

	cmd

### 退出cmd通过命令 exit ###

	exit

### Cmd.exe 通过 /c 来接收命令参数 ###

	Cmd.exe /c
	Cmd.exe /c help

### 启动外部程序 ###

	notepad

	wordpad

因为notepad.exe位于C:Windows\system32 这个目录，而这个目录已经默认被包含在Powershell的环境变量$env:Path中。  
而wordpad.exe 所在的“%ProgramFiles%\Windows NT\Accessories\wordpad.exe“目录却没有包含，可以先进入这个目录，再运行wordpad，或者将wordpad所在的目录加入到环境变量中，$env:Path=$env:Path+”%ProgramFiles%\Windows NT\Accessories”。


参考：

* [PowerShell 在线教程 - PowerShell 中文博客](http://www.pstips.net/powershell-online-tutorials/)
* [PowerShell 3.0 入门教程 - PowerShell 中文博客](http://www.pstips.net/powershell-v3-basic/)
* [PowerShell 中文博客 - 收集和分享 Windows PowerShell 相关教程,技术和最新动态](http://www.pstips.net)
* [PowerShell入门介绍教程 - PowerShell - 洪哥笔记](http://www.splaybow.com/post/powershellintro.html)
* [PowerShell入门（一）：PowerShell能干什么？ - Luke Zhang - 博客园](http://www.cnblogs.com/ceachy/archive/2013/01/30/WhatCanPowerShellDo.html)
* [Powershell基础教程：变量、循环、基本命令 - Lesca 技术宅](https://lesca.me/archives/powershell-tutorial-basics.html)
* [Windows PowerShell 初学者入门教程 - PowerShell & DOS - 大家论坛](http://club.topsage.com/thread-482647-1-1.html)
* [经典PowerShell入门教程_百度文库](https://wenku.baidu.com/view/39f9f7d5195f312b3169a5ed.html?re=view)





参考： 

* [Powershell方法（对象能做什么） - PowerShell 中文博客](http://www.pstips.net/powershell-methods.html)
* [PowerShell入门（一）：PowerShell能干什么？ - 51CTO.COM](http://os.51cto.com/art/201302/380175.htm)
* [使用PowerShell可以做那些有趣的事情? - 知乎](https://www.zhihu.com/question/46435308)
* [PowerShell 与 cmd 有什么不同？ - 知乎](https://www.zhihu.com/question/22611859)
* [我能用Windows PowerShell做什么：暂停 Windows PowerShell 脚本 - CSDN博客](http://blog.csdn.net/itanders/article/details/1785715)
* [我能用Windows PowerShell做什么：列出你所有的 Windows PowerShell 别名 - CSDN博客](http://blog.csdn.net/itanders/article/details/1783894)
* [我能用Windows PowerShell做什么：写一个讯息到控制台窗口 - CSDN博客](http://blog.csdn.net/itanders/article/details/1784187)
