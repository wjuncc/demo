---
layout: post
title:  "powershell创建winForm"
date:   2017-12-08 20:25:46 +0800
categories:  
tags: powershell
---

# powershell创建winForm #

[PowerShell 在线图形设计器，可以快速地创建代码](http://www.poshgui.com/) 





git搜索：Csv  GridView example  language:PowerShell

### 测试1 ###
测试：https://github.com/mpearon/PowerShell/blob/e5a1882fb8a49acedd5015f3f06f1872a9fda9e7/Personal/ScratchPad/Select-FromGridView.ps1

报错：

	PS C:\Users\Administrator> E:\n\wj\171207_blogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f06f1872a9fda9e7\Personal\ScratchPad\Select-FromGridView.ps1
	无法加载文件 E:\n\wj\171207_blogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f0
	6f1872a9fda9e7\Personal\ScratchPad\Select-FromGridView.ps1。文件 E:\n\wj\171207_bl
	ogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f06f1872a9fda9e7\Personal\
	ScratchPad\Select-FromGridView.ps1 未进行数字签名。不会在系统上执行该脚本。有关详细信息，请参阅 http://go.mic
	rosoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
	    + CategoryInfo          : SecurityError: (:) []，ParentContainsErrorRecordE 
	   xception
	    + FullyQualifiedErrorId : UnauthorizedAccess
	
	PS C:\Users\Administrator> 


在PowerShell执行以下输入： 

查看当前策略：

	Get-ExecutionPolicy

返回

	PS C:\Users\Administrator> Get-ExecutionPolicy 
	RemoteSigned

修改当前策略：

	set-ExecutionPolicy Unrestricted
	回车

listary 快捷键：ISE

 
### 测试2 ###
https://github.com/masters274/Posh_Repo/tree/8ae45da25bc425b18aff1924ac7396a3d34cdee8


#### 参考 ####

* 在线ui
* [PowerShell 技能连载 - 在 PowerShell 中创建 WinForms GUI 界面 - 叹为观止](http://blog.vichamp.com/2016/12/23/creating-winforms-guis-in-powershell/)
* [PowerShell 技能连载 - 创建简单的 UI - 叹为观止](http://blog.vichamp.com/2016/12/28/creating-simple-uis/)
* [PowerShell 技能连载 - 调整简单界面 - 叹为观止](http://blog.vichamp.com/2016/12/28/adjusting-simple-uis/)
* [www.tk4479.net/FrankGGH/article/details/7334924](http://www.tk4479.net/FrankGGH/article/details/7334924)
* UI自动化：
* [powershell推荐阅读:使用 Windows PowerShell 实现 UI 自动化 - YOKE-HOME](https://yoke88.wordpress.com/2007/12/13/powershell推荐阅读使用-windows-powershell-实现-ui-自动化/)
* 计划任务：
* [启动powershell脚本在远程机器运行_百度知道](https://zhidao.baidu.com/question/538894308.html)
* GridView 显示csv
* [Out-GridView官方用法](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-5.1)
* git搜索
* Csv  GridView  language:PowerShell
* 
* winForm1
* [使用Windows PowerShell创建WinForm程序 - clowwindy - 博客园](http://www.cnblogs.com/clowwindy/archive/2009/05/06/1450344.html)
* [使用Windows PowerShell创建WinForm程序 - 亚伦的日志 - 网易博客](http://25ie.blog.163.com/blog/static/1026232112010213027499/)
* [使用Windows PowerShell创建WinForm程序 - 阿里云](https://yq.aliyun.com/wenji/97517)
* winForm2
* [Powershell创建WinForm应用程序 - 与你心飞 - ITeye博客](http://hongzhguan.iteye.com/blog/1471953)
* git搜索 
* Function Show-WinForm language:PowerShell 
* Function Show WinForm example language:PowerShell 
* Function Grid WinForm example language:PowerShell 
* 
* pdf
* http://m.jb51.net/books/209514.html
* [Dealing with Powershell Inputs via Basic Windows Form](https://www.codeproject.com/Articles/799161/Dealing-with-Powershell-Inputs-via-Basic-Windows-F)
* [使用Windows PowerShell创建WinForm程序-代码之家](http://www.daima234.com/8/14236.html)
* [在powershell函数中，非模态窗体创建_winforms_帮酷编程问答](https://ask.helplib.com/.net/post_3798940)