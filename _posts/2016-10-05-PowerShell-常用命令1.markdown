---
layout: post
title:  "PowerShell 常用命令1"
date:   2016-10-05 21:17:32 +0800
categories:  
tags: 
    - powershell 

---


## 本地测试时候，打开localhost ##
例如，react案例设置的默认端口是8080
```powershell
Start-Process chrome.exe http://localhost:8080
```

## powerShell将打印结果输出到txt文件 ##

### cmd ###
最简单的是
```powershell
	get-childitem c:\windows
```
改成
```powershell
	get-childitem c:\windows > C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt
```
这其实是一个cmd命令。cmd重定向。

### powerShell ###

	get-childitem c:\windows | Out-File C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt
	get-content  C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt

可指定编码：

	get-childitem c:\windows | Out-File -encoding "Default" -filepath "C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt"

指定ascii，

	get-childitem c:\windows | Out-File -encoding "ascii" -filepath "C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt"

效果不好，C:\windows 显示为 ??:\windows

注意不写 gbk2312
	
	get-childitem c:\windows | Out-File -encoding "gbk2312" -filepath "C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt"

	Out-File : 无法对参数“Encoding”执行参数验证。参数“gbk2312”不属于 ValidateSet 属性指定的集合“unknown,string,unicode
	,bigendianunicode,utf8,utf7,utf32,ascii,default,oem”。请提供一个此集合中的参数，然后重试此命令。
	所在位置 行:1 字符: 47
	+ get-childitem c:\windows | Out-File -encoding "gbk2312" -filepath "C:\Python27\L ...
	+                                               ~~~~~~~~~
	    + CategoryInfo          : InvalidData: (:) [Out-File]，ParameterBindingValidationException
	    + FullyQualifiedErrorId : ParameterArgumentValidationError,Microsoft.PowerShell.Commands.OutFileCommand
	
## Powershell使用OpenFileDialog打开文件 ## 


	function Show-OpenFileDialog
	{
	  param
	  ($Title = 'Pick a File', $Filter = 'All|*.*|PowerShell|*.ps1')
	  
	  $type = 'Microsoft.Win32.OpenFileDialog'
	  
	  
	  $dialog = New-Object -TypeName $type 
	  $dialog.Title = $Title
	  $dialog.Filter = $Filter
	  if ($dialog.ShowDialog() -eq $true)
	  {
	    $dialog.FileName
	  }
	  else
	  {
	    Write-Warning 'Cancelled'
	  }
	}

###### 参考 ######

* [PowerShell 2.0 实践（一）操作文件系统 - 徐州瑞步科技 - 博客园](http://www.cnblogs.com/brooks-dotnet/archive/2010/07/18/1780146.html)
* [Powershell使用OpenFileDialog打开文件示例_PowerShell_脚本之家](http://m.jb51.net/article/62849.htm)
* [Powershell使用OpenFileDialog打开文件示例 - 新客网](http://www.xker.com/page/e2015/03/171168.html)
* [Powershell使用OpenFileDialog - PowerShell 中文博客](http://www.pstips.net/using-the-openfile-dialog.html)
* [Powershell使用OpenFileDialog打开文件示例 - 技术文档 - 乐码库下载站](http://www.lemaku.com/tech/other/201611/89049.html) 
* [PowerShell 多行输入对话框、打开文件对话框、文件夹浏览对话框、输入框及消息框 - 叹为观止](http://blog.vichamp.com/2013/10/15/powershell-multi-line-input-box-dialog-open-file-dialog-folder-browser-dialog-input-box-and-message-box/)
* [Powershell使用OpenFileDialog打开文件示例_PowerShell_脚本之家天蓬元帅,李书文,奇迹暖暖梦恋奇迹原创_搜搜看-www.ezmap.cn](http://www.ezmap.cn/page/www_jb51_net/article/62849.htm)
* [Powershell使用 OpenFileDialog类 假死问题解决。 / 源码寺](https://www.yuanmas.com/info/NmODgMZXyx.html)
* [Powershell 输出文本到文件：echo - out-file](http://martual.leanote.com/post/Untitled-54c6b0ae38f41110370023e7-21)
* [PowerShell输出字符串到文件 - PowerShell - 洪哥笔记](http://www.splaybow.com/post/powershell-out-file.html)
* [powershell如何将write-host结果输出到文件_百度知道](https://zhidao.baidu.com/question/134604827855346325.html)
* [如何在PowerShell中输出内容_windows_帮酷编程问答](https://ask.helplib.com/windows/post_440344)
* [使用 Out Cmdlet 重定向数据 - Microsoft Docs](https://docs.microsoft.com/zh-cn/powershell/scripting/getting-started/cookbooks/redirecting-data-with-out---cmdlets?view=powershell-5.1)
* [我把脚本执行的结果输出到文本，但是看不到 - PowerShell 中文博客](http://www.pstips.net/question/4008.html)
* [有关PowerShell脚本你必须知道的十个基本概念 - 51CTO.COM](http://os.51cto.com/art/201101/244228.htm)
* [Powershell 语法总结 - 堕落天使的日志 - 网易博客](http://gaojianzhuang110.blog.163.com/blog/static/1861314620108290363775/)


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