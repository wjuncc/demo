---
layout: post
title:  "Powershell 使用OpenFileDialog打开文件 - Google 搜索"
date:   2017-10-05 21:17:32 +0800
categories:  
tags: Powershell
---

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