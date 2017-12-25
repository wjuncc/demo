---
layout: post
title:  "运行powerShell"
date:   2017-10-05 21:17:32 +0800
categories:  
tags: 
    - powershell

---

# 运行powerShell #

报错

无法加载文件 因为在此系统上禁止运行脚本


### 例子1 ###
打印当前运行的进程，以公司分类：

	# PowerShell cmdlet to group Processes by company
	$Path = "D:\PowerShell\ProcessCompany.txt"
	$ProSvc = get-Process |sort company |ft -groupby company 
	$ProSvc
	# $ProSvc | out-file $Path

注意，没有输出到ProcessCompany.txt

### 例子2 ###
	get-childitem c:\windows

powerShell将打印结果输出到txt文件
	
	get-childitem c:\windows > C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt


#### 参考 ####

* [2. 三种运行Powershell代码的方法-一万小时-ICSEC-51CTO博客](http://blog.51cto.com/jamesoujj/185136)
* [PowerShell让系统可以执行.ps1文件 - PowerShell - 洪哥笔记](http://www.splaybow.com/post/powershellexecps1.html)
* [如何让PowerShell运行脚本 ？_windows_帮酷编程问答](https://ask.helplib.com/windows/post_134766)
* [如何运行PowerShell的脚本文件 - 中道学友 - 博客园](http://www.cnblogs.com/awpatp/archive/2012/07/17/2595018.html)
* [如何运行PowerShell的脚本文件 - CSDN博客](http://blog.csdn.net/lyncai/article/details/8259223)
* [在cmd中直接运行PowerShell脚本文件的方法，_基础教程 - 帮客之家](http://www.bkjia.com/jcjc/930514.html)
* [查看和运行 Windows PowerShell 脚本](https://technet.microsoft.com/zh-cn/library/cc917925.aspx)