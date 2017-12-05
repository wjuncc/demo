---
layout: post
title:  "修改系统盘符 powerShell"
date:   2013-03-04 14:01:12 +0800
categories: jekyll update
cats: Powershell
---

# 修改系统盘符 powerShell #
  
### CMD 修改盘符 ###

很好

	@echo off
	color f4
	echo 特别提醒! 请不要修改C: !&PAUSE>NUL
	COLOR 07
	cls
	
	set/p a=请输入原盘符……  
	set/p b=请输入新盘符……  
	set old=%a%:
	set new=%b%:
	
	pushd %new% 2>nul && echo %new%盘已经存在! && pause && goto :eof
	
	for /f %%i in ('mountvol %old% /l') do set "vol=%%i"
	mountvol %old% /d
	mountvol %new% %vol%

	popd


### powerShell 获取所有盘符 ###

	#requires -Version 1
	[Environment]::GetLogicalDrives()

### powerShell 获取本机系统盘符 ###

	在cmd中为：
	echo %systemdrive%

	在Powershell中：
	$env:SystemDrive

	在c#中：
	Environment.GetEnvironmentVariable(“SystemDrive”);



### powerShell 获取网络系统盘符 ###

备份一下

	static void Main(string[] args)
	{
	    string mgmtPath = @"NetworkComputerNamerootcimv2";
	
	    ManagementClass mc = new ManagementClass(mgmtPath, @"Win32_LogicalDisk", null);
	    Console.WriteLine(mc.GetInstances().Cast< ManagementBaseObject >().Where(
	        mbo => mbo.Properties["DriveType"].Value.ToString() == "3").First().Properties["DeviceID"].Value.ToString());
	}




参考：

* [powertips](http://community.idera.com/powershell/powertips)
* [批处理：更改盘符 - PowerShell & DOS - 大家论坛](http://club.topsage.com/thread-1738868-1-1.html) 
* [获取网络上机器的系统盘符 - PowerShell 中文博客](http://www.pstips.net/network-machine-system-drive.html)
* [Powershell获取所有盘符 - PowerShell 中文博客](http://www.pstips.net/find-all-active-drive-letters.html) 
* [Powershell中获取所有磁盘盘符的方法](http://www.jb51.net/article/63885.htm)
