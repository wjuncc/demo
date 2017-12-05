---
layout: post
title:  "powerShell将打印结果输出到txt文件"
date:   2017-10-05 21:17:32 +0800
categories:  
tags: 
---

# powerShell将打印结果输出到txt文件 #

### cmd ###
最简单的是

	get-childitem c:\windows

改成
	
	get-childitem c:\windows > C:\Python27\Lib\site-packages\wj7\etc\blog\log.txt

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
	
#### 参考 ####

* [Powershell 输出文本到文件：echo - out-file](http://martual.leanote.com/post/Untitled-54c6b0ae38f41110370023e7-21)
* [PowerShell输出字符串到文件 - PowerShell - 洪哥笔记](http://www.splaybow.com/post/powershell-out-file.html)
* [powershell如何将write-host结果输出到文件_百度知道](https://zhidao.baidu.com/question/134604827855346325.html)
* [如何在PowerShell中输出内容_windows_帮酷编程问答](https://ask.helplib.com/windows/post_440344)
* [使用 Out Cmdlet 重定向数据 - Microsoft Docs](https://docs.microsoft.com/zh-cn/powershell/scripting/getting-started/cookbooks/redirecting-data-with-out---cmdlets?view=powershell-5.1)
* [我把脚本执行的结果输出到文本，但是看不到 - PowerShell 中文博客](http://www.pstips.net/question/4008.html)
* [有关PowerShell脚本你必须知道的十个基本概念 - 51CTO.COM](http://os.51cto.com/art/201101/244228.htm)
* [Powershell 语法总结 - 堕落天使的日志 - 网易博客](http://gaojianzhuang110.blog.163.com/blog/static/1861314620108290363775/)