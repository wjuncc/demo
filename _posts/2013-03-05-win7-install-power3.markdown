---
layout: post
title:  "win7 安装 powerShell3"
date:   2013-03-04 14:01:12 +0800
categories: jekyll update
cats: Powershell
---

# win7 安装 powerShell3 #

### 查詢Powershell目前版本 ###

查詢Powershell目前版本。有2种方式：

	Get-Host

	$PSVersionTable


返回数据内容一样，格式不同：

Get-Host

	PS C:\Users\Administrator> Get-Host


	Name             : ConsoleHost
	Version          : 2.0
	InstanceId       : 9ac9f01c-7caa-4db9-8049-df2c9a4a61a5
	UI               : System.Management.Automation.Internal.Host.InternalHostUserI
	CurrentCulture   : zh-CN
	CurrentUICulture : zh-CN
	PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
	IsRunspacePushed : False
	Runspace         : System.Management.Automation.Runspaces.LocalRunspace

$PSVersionTable

	PS C:\Users\Administrator> $PSVersionTable

	Name                           Value
	----                           -----
	CLRVersion                     2.0.50727.5485
	BuildVersion                   6.1.7601.17514
	PSVersion                      2.0
	WSManStackVersion              2.0
	PSCompatibleVersions           {1.0, 2.0}
	SerializationVersion           1.1.0.1
	PSRemotingProtocolVersion      2.1



### 复制powershell窗口代码 ###
1. 左键点击CMD处理程序左上角，选择属性。（或者按下Alt+空格）。
2. 选中快速编辑模式，点击确定。


安装后要重启系统。


参考：

* [在 Windows 7 和 Windows Server 2008 R2 上安装 Windows PowerShell 3.0-SQL Server Deep Dive-51CTO博客](http://blog.51cto.com/ultrasql/1615299)
* [下载并安装 Windows PowerShell 3.0 - Office 支持](https://support.office.com/zh-cn/article/下载并安装-Windows-PowerShell-3-0-d739cd71-3c18-42ea-879f-b408bf53b1f4)
* [Windows Powershell 介绍和安装，windowspowershell_基础教程 - 帮客之家](http://www.bkjia.com/jcjc/868261.html)
* [PowerShell 3.0 安裝檔案 @ 三花摺耳貓； :: 痞客邦 PIXNET ::](http://nathanmint.pixnet.net/blog/post/184370916-powershell-3.0-安裝檔案-)
* [Powershell 介绍和安装 - PowerShell 中文博客](http://www.pstips.net/powershell-introduction-and-install.html)
* [bet36体育在线-bet36在线投注-bet36体育在线老网站](http://www.angbaimiu.com/bzh.php)
* [Windows Powershell版本 @ 學海無邊，書囊無底 :: 痞客邦 PIXNET ::](http://mydiamond.pixnet.net/blog/post/60521317-windows-powershell版本)


* [2. 三种运行Powershell代码的方法-一万小时-ICSEC-51CTO博客](http://blog.51cto.com/jamesoujj/185136)
* [一键帮你复制多个文件到多个机器——PowerShell小脚本](https://feed.baidu.com/feed/data/wise/landingpage?s_type=news&dsp=wise&nid=3311648503046902494&n_type=&p_from=4)
* [为什么微软直到 Windows 10 才在命令行里支持 Ctrl+V 粘贴？ - 知乎](https://www.zhihu.com/question/25649766)
* [一个前端程序猿的Sublime Text3的自我修养 - 三省吾身丶丶](http://blog.guowenfh.com/2015/12/26/SublimeText/)
* [怎样复制粘贴windows命令行中的内容 . - CSDN博客](http://blog.csdn.net/xianrenyingzi/article/details/8597097)
* [在CMD命令行和PowerShell中实现复制粘贴功能 - 张世辉 - CSDN博客](http://blog.csdn.net/crazygolf/article/details/37907511)
* [怎样复制粘贴windows命令行中的内容 - CSDN博客](http://blog.csdn.net/xiaoxiaoniaoer1/article/details/7496841)
* [怎么复制cmd的内容 - CSDN博客](http://blog.csdn.net/zl544434558/article/details/18982515)
* [复制命令/powershell窗口屏幕缓冲区_c++_帮酷编程问答](https://ask.helplib.com/c++/post_2023949)


