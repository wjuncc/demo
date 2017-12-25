---
layout: post
title:  "第一次运行PowerShell报错"
date:   2016-08-05 21:17:32 +0800
categories:  
tags: 
    - powershell

---

# 无法加载文件 因为在此系统上禁止运行脚本 #

首次在计算机上启动 Windows PowerShell 时，现用执行策略很可能是 Restricted（默认设置）。

Restricted 策略不允许任何脚本运行。

查看当前执行策略：

	get-executionpolicy

修改执行策略：

	set-executionpolicy remotesigned


	执行策略更改
	执行策略可帮助你防止执行不信任的脚本。更改执行策略可能会产生安全风险，如 http://go.microsoft.com/fwlink/?LinkID=135170
	中的 about_Execution_Policies 帮助主题所述。是否要更改执行策略?
	[Y] 是(Y)  [N] 否(N)  [S] 挂起(S)  [?] 帮助 (默认值为“Y”):

输出

	This is a message

### 备录 ###

文件 test_ps.ps1  

	Write-Host "This is a message"

完整错误代码


	PS C:\Users\Administrator> C:\Python27\Lib\site-packages\wj7\etc\blog\test_ps.ps1
	C:\Python27\Lib\site-packages\wj7\etc\blog\test_ps.ps1 : 无法加载文件 C:\Python27\Lib\site-packages\wj7\etc\blog\test_p
	s.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 http://go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execut
	ion_Policies。
	所在位置 行:1 字符: 1
	+ C:\Python27\Lib\site-packages\wj7\etc\blog\test_ps.ps1
	+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
	    + CategoryInfo          : SecurityError: (:) []，PSSecurityException
	    + FullyQualifiedErrorId : UnauthorizedAccess

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
* [PowerShell因为在此系统中禁止执行脚本解决方法 - Asharp - 博客园](http://www.cnblogs.com/zhaozhan/archive/2012/06/01/2529384.html)
* [Powershell中禁止执行脚本解决办法 - 张善友 - 博客园](http://www.cnblogs.com/shanyou/archive/2011/09/03/2165371.html)
* [PowerShell在此系统中禁止执行脚本解决方法 - Zhen Happy 的博客](http://zhenhappy.github.io/2015/11/12/PowerShell/PowerShell-Restricted/)
* [PowerShell 无法加载文件ps1，因为在此系统中禁止执行脚本 - CSDN博客](http://blog.csdn.net/xumengxing/article/details/6897288)
* [PowerShell因为在此系统中禁止执行脚本解决方法 - 仙](https://blog.cnlabs.net/6158.html)
* [PowerShell因为在此系统中禁止执行脚本解决方法 – Will的博客](http://www.94will.com/2016/01/690.html)
* [解决PowerShell无法加载文件因为在此系统上禁止运行脚本 - 简书](http://www.jianshu.com/p/e5214b3a7627)
* [PowerShell 因为在此系统中禁止执行脚本 - 诸神的黄昏](https://www.ragnaroks.org/life/powershell-enable-exec-script.html)
* [Powershell中的执行策略(Execution Policy) - Leona+](https://leonax.net/p/1273/execution-policy-in-powershell/)
* [Powershell直接脚本时出现无法加载文件因为禁止执行脚本_PowerShell_脚本之家](http://www.jb51.net/article/53643.htm)