---
layout: post
title:  "Powershell使用指定程序打开文件"
date:   2017-10-05 21:17:32 +0800
categories:  
tags: 
    - Powershell
---


## Powershell使用指定程序打开文件 ## 

#### 设置系统时间 ####

	Set-Date -date "2016-12-01 8:30 AM"


#### 调整系统时间 ####

	Set-Date (Get-Date).AddDays(2)

#### 判断文件是否存在 ####

	Test-Path c:\PowerShell.xlsx

### 重命名文件 ###

	Rename-Item c:\PowerShell.xlsx New_PowerShell.xlsx

### 移动文件和文件夹 ###

	Move-Item c:\PowerShell.xlsx d:\PowerShell.xlsx

	Move-Item c:\*.xls d:\excel\


### 打开程序 ###

	Invoke-Item c:\Windows\System32\notepad.exe


### 批量打开文件 ###
	Invoke-Item c:\Sysgeek\*.txt


### 读取文本文件 ###

	Get-Content c:\Sysgeek\Hello.txt

仅仅预览

	Get-Content c:\Sysgeek\Hello.txt -totalcount 1

### 添加文本内容 ###

	Add-Content c:\Sysgeek\Hello.txt "by wj"

### 统计文本文件 ###

	Get-Content c:\Sysgeek\Hello.txt | Measure-Object


### 服务状态统计 ###

	Get-Service

统计当前所有已停止的服务：

	Get-Service | Where-Object {$_.status -eq "stopped"}

### 重启服务 ###

	Restart-Service Dnscache

	Restart-Service -displayname "DNS Client"

### 更改服务启动状态 ###

	Set-Service Dnscache -startuptype "manual"


### 强制刷新Windows 10 Apps ###
		
	Get-AppXPackage -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}

### 复制文件 ###

	Copy-Item c:/scripts c:/Test –recurse



### cmd ###


打开淘客助手.bat

	start explorer http://www.iqiyi.com


打开爱奇艺.bat

	start explorer http://www.taokezhushou.com



###### 参考 ######

* [PowerShell查看打开文件的默认应用程序 - PowerShell 中文博客](http://www.pstips.net/finding-executable.html)
* [Windows PowerShell ISE 的键盘快捷方式 - Microsoft Docs](https://docs.microsoft.com/zh-cn/powershell/scripting/core-powershell/ise/keyboard-shortcuts-for-the-windows-powershell-ise?view=powershell-5.1)
* [Windows 10中常用的15项PowerShell高级任务  系统极客](https://www.sysgeek.cn/windows-10-powershell-advanced-task/)
* [书摘——WindowsPowerShell复制文件或文件夹_zhuningxianjn_新浪博客](http://blog.sina.com.cn/s/blog_c3aa886b0102wsst.html)
* [Win下必备神器之Cmder - 晚晴幽草轩](https://jeffjade.com/2016/01/13/2016-01-13-windows-software-cmder/)