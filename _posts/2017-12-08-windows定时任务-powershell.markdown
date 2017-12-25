---
layout: post
title:  "windows定时任务 powershell"
date:   2017-12-08 05:31:56 +0800
categories:  
tags: 
    - powershell

---

# windows定时任务 powershell #

## 创建 ##
powershell create task scheduler   
Windows PowerShell ISE



# Windows PowerShell ISE 介绍 #

* [Powershell快速入门（一） 安装和使用 - 简书](http://www.jianshu.com/p/c8f5c374466a)
* [不一样的命令行 – Windows PowerShell简介 - grapeot - 博客园](http://www.cnblogs.com/grapeot/archive/2010/02/22/1670822.html)
* 
## 修改 ##

用CMD命令 schtasks 创建一个计划任务

	
	Get-Command -Module ScheduledTasks

无反应：

	PS C:\Users\Administrator> Get-Command -Module ScheduledTasks
	PS C:\Users\Administrator>

Windows的计划任务不能直接调用PowerShell脚本来执行

Windows的计划任务->bat->PowerShell脚本

	powershell E:\FTPbackup\del-expired.ps1


#### 参考 ####


* [Use PowerShell to Create Scheduled Tasks – Hey, Scripting Guy! Blog](https://blogs.technet.microsoft.com/heyscriptingguy/2015/01/13/use-powershell-to-create-scheduled-tasks/)
* [New-ScheduledTask](https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/new-scheduledtask?view=win10-ps)
* [使用批处理及Windows计划任务做每日备份 - Edi Wang](http://edi.wang/post/2012/6/5/daily-backup-using-batch-and-task-schedule-in-windows)
* [【Windows】设置每分钟执行一次bat脚本的计划任务 - 枫芸志](http://witmax.cn/windows-run-bat-per-minute.html)
* [Windows 自动定时执行任务的几种实现方法 - 博弈无涯 - 博客园](http://www.cnblogs.com/bmwchampion/archive/2010/08/21/autotimingexcutejob.html)
* [Windows中实现定时自动运行程序](http://vod.sjtu.edu.cn/help/Article_Print.asp?ArticleID=1209)
* [windows定时任务bat怎么写_百度知道](https://zhidao.baidu.com/question/1963027420188559780.html)
* [Windows定时调用bat执行Java程序 - greatwqs : Where amazing happens ... - ITeye博客](http://greatwqs.iteye.com/blog/1310626)
* [如何设置PowerShell脚本定时执行](https://social.microsoft.com/Forums/zh-CN/a8014b07-0654-4461-8afb-74cabe334198/powershell?forum=windowsserversystemzhchs)
* [在Windows下利用PowerShell脚本定时删除过期文件  Hey! Linux.](http://heylinux.com/archives/1234.html)
* [PowerShell 管理计划任务 - PowerShell 中文博客](http://www.pstips.net/powershell-manipulating-scheduled-tasks.html)
* [powershell 如何定时执行 ps1_百度知道](https://zhidao.baidu.com/question/239480237535013164.html)
* [PowerShell添加修改任务计划 - PowerShell - 洪哥笔记](http://www.splaybow.com/post/powershell-mod-schedule-task.html)
