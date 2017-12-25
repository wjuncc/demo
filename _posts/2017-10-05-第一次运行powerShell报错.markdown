---
layout: post
title:  "第一次运行PowerShell报错"
date:   2017-10-05 21:17:32 +0800
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


#### 参考 ####

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