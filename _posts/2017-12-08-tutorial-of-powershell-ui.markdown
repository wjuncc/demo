---
layout: post
title:  "tutorial of powershell ui"
date:   2017-12-08 21:41:26 +0800
categories:  private
tags: powershell
---

# windows powershell实战指南 pdf #

tutorial from [codeproject](https://www.codeproject.com/Articles/799161/Dealing-with-Powershell-Inputs-via-Basic-Windows-F)

## 目录 ##
* 介绍
* 选择？！
* 背景
* 使用代码
	* 多选择提示
	* 超时提示
	* 从复选框和Radiobutton组收集选择
	* 选中列表框选择
	* 手风琴菜单
	* 多选框Combobox
	* 条形图
	* 图表的实际数据
	* 线，bar和饼图
	* Data Grid概念
	* 列表视图
	* 填充GridView数据表
	* 名单与可折叠的组
	* 拖放
	* 上下滚动
	* Ribbon 按钮
	* 自定义调试消息框
	* 杂项。 密码输入
		* Plain
		* 活动目录
		* 会话Cookie
	* 通用对话框
	* 带有输入焦点控制的选项卡式对话框
	* 进度条
	* 计时器
	* 任务列表进度
	* 圈进度指标
	* 文件系统TreeView
	* 嵌入XAML
		* ...on the fly
		* 更多
	* 连接WPF事件
	* 树视图
		* Plain
		* 高级
			* 自定义图标
			* 背景工作者
			* DropDown组合框
			* Tabbed分页
			* 三态树视图
			* 标签项目的一棵树
	* 系统托盘通知图标
	* Selenium 测试
	* Selenium IDE IDE Powershell格式
	* 通用Selenium自动化
	* 用Selenium sendKeys上传文件
	* 杂项。 使用WebDriver
	* 在资源管理器任务栏上显示Selenium调试消息
	* Selenium EventFiring WebDriver示例
* 杂项。 工具包
	* 截图
	* 隐藏Powershell控制台
* 在Powershell ISE中编写Selenium脚本
* 极端情况
* 解剖过程
	* 初步讨论
	* 实际转换到Powershell
* GitHub上的源代码
* 历史

## 介绍 ##

Powershell是一种高级脚本框架，通常脚本是在控制台主机上运行的，通常是远程运行的，但Powershell脚本仍然是在Windows计算机上交互使用的。 
当通用脚本执行时，可能需要选择多个选项。
需要以级联的方式向用户提供多个选项，通常需要复杂的选择场景。 
对于某些数据选择，GUI比CLI更直观，更快 - 在控制台中，即使是基本的选择,看起来也不美观。

对于很多情况，普通的旧式Windows窗体仍然是提示用户的一种方便的方式。 
这是本文的重点。
我们从[http://www.java2s.com/](http://www.java2s.com/)中找几个基本例子，并将它们转换为Powershell。
之后，我们使用较早的样本作为更复杂的构件。 
事实上，这些例子中的所有代码都可以在一个单独的文件中使用，而且不需要独立的设计器代码，这大大简化了转换。
重点在于，在处理提示，密码，复选框，单选框，检查列表，网格，树形视图，选项卡式对话框以及这些组合的各种数据的时候，将新的Powershell代码保持选择场景所需的最低限度。
此外，还将演示表单元素特定的事件处理程序将执行PowerShell代码。
最后，像TreeView这样的控件可以很好地对数据进行可视化处理，而不必反复提示。

另一方面，Windows Presentation Foundation调试起来或多或少有些累，但能用 - 文章中间部分提供了示例。
与WPF交互需要多线程，这种技术对于长时间运行的脚本的异步状态报告也是有价值的。

令人愉快的是，所有的脚本都能在最小服务器接口中运行，甚至在服务器核心[Windows Server 2012](https://4sysops.com/archives/switch-windows-server-2012-gui-layers-with-powershell/)图形用户界面中也能正常运行。 
原因是:虽说“移除”了“Server Graphical Shell(服务器图形外壳)”和“Server Graphical Management Tools & Infrastructure(服务器图形管理工具和基础设施)”的Windows功能，但仍然保留了完整的微软.Net框架。 
Windows Server Core仍然可以满足为复杂的自定义数据提供熟悉的用户界面的示例的最终目标。 
请注意，因为“Server Core”能用鼠标，因此，不用给表单元素添加键盘快捷键。

在稍后的例子中，显示了如何手动构建Powershell Selenium脚本（等价于C＃）或自动在Selenium IDE中记录; 
进一步肯定了使用Powershell运行Selenium录制的好处。

最后，手把手的做转换练习。

## 背景 ##
我们认识到Powershell代码的版本迭代实际上与C＃版本相同，只是语义有差异。
作者的github代码[sergueik/powershell_ui_samples](https://github.com/sergueik/powershell_ui_samples), 每天会跟进新开发的代码。

我们目前需要构建一个辅助类，负责将信息传递给Powershell脚本调用程序，并以事件处理程序的形式提供给Windows窗体，尽管所有对话框都将以模态方式绘制。
如果没有这种紧密的联系，很有可能会产生难以调试的错误。
在作者以后的文章中，再来谈论对此问题的分析。

## 使用代码 ##
文中的样本代码，是为了更容易让读者理解而写的。

## 代码细节 ##
该类是非常基础的，用于把表单窗口的信息传给Powershell。
它只需要实现IWin32Window接口; 
它也将有各种私人数据成员与getter和setter和方法 - 如下所示。

	Add-Type -TypeDefinition @"

	// "
	using System;
	using System.Windows.Forms;
	public class Win32Window : IWin32Window
	{
	    private IntPtr _hWnd;
	    private int _data;
	
	    public int Data
	    {
	        get { return _data; }
	        set { _data = value; }
	    }
	
	    public Win32Window(IntPtr handle)
	    {
	        _hWnd = handle;
	    }
	
	    public IntPtr Handle
	    {
	        get { return _hWnd; }
	    }
	}

	"@ -ReferencedAssemblies 'System.Windows.Forms.dll'



Powershell在类中存储了自己的窗口句柄：

	if ($process_window -eq $null ){
	  $process_window = New-Object Win32Window -ArgumentList
	  ([System.Diagnostics.Process]::GetCurrentProcess().MainWindowHandle)
	}

从$caller.Message和$caller.Data读取条目选择和总体状态:

	$DebugPreference = 'Continue'

	  if($process_window.Data -ne $RESULT_CANCEL) {
	    write-debug ('Selection is : {0}' -f  , $process_window.Message )
	  } else {
	    write-debug ('Result is : {0} ({1})' -f
	    $Readable.Item($process_window.Data) , $process_window.Data )
	  }

换种语法可以写作：

	$guid = [guid]::NewGuid()
	
	$helper_namespace = ("Util_{0}" -f ($guid -replace '-',''))
	$helper_name = 'Helper'
	
	Add-Type -UsingNamespace @(
	  'System.Drawing',
	  'System.IO',
	  'System.Windows.Forms',
	  'System.Drawing.Imaging',
	  'System.Collections.Generic',
	  'System.Text' `
	  ) `
	   -MemberDefinition @"
	// inline C# code without class decoration
	"@ -ReferencedAssemblies @( 'System.Windows.Forms.dll',`
	     'System.Drawing.dll',`
	     'System.Data.dll',`
	     'System.Xml.dll') `
	   -Namespace $helper_namespace -Name $helper_name -ErrorAction Stop
	
	$helper = New-Object -TypeName ('{0}.{1}' -f $helper_namespace,$helper_type)
	# the rest of Powershell code 




这样就不用担心每次修改内联C＃代码时都会看到恼人的警告：

	Add-Type : Cannot add type. The type name 'Win32Window' already exists.
	At C:\developer\sergueik\powershell_ui_samples\treeview_c.ps1:21 char:1
	+ Add-Type -TypeDefinition @"


注意，默认包含了名称空间，不应该在调用agrit中明确提供


	Warning as Error:
	The using directive for 'System' appeared previously in this namespace
	The using directive for 'System.Runtime.InteropServices' appeared previously in this namespace


#### 参考 ####

* [使用格式命令更改输出视图 - Microsoft Docs](https://docs.microsoft.com/zh-cn/powershell/scripting/getting-started/cookbooks/using-format-commands-to-change-output-view?view=powershell-5.1)
* [PowerShell-第1章 交互界面 - lucky_zhang - 博客园](http://www.cnblogs.com/yajing-zh/p/4711404.html)
* [Powershell格式化输出 - ITGirl笑笑 - 博客园](http://www.cnblogs.com/ITGirlXiaoXiao/archive/2012/08/06/2624851.html)
* [Displaying Output in a GUI Application – SAPIEN Blog](https://www.sapien.com/blog/2014/12/15/display-output-in-a-gui-application-copy/)
* [Creating a GUI for CSV Data – SAPIEN Blog](https://www.sapien.com/blog/2015/01/19/creating-a-gui-for-csv-data/)
* [Out-GridView](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-5.1)
* [Add Custom Output to Windows PowerShell GridView](http://www.itprotoday.com/management-mobility/add-custom-output-windows-powershell-gridview)
* [PowerShell "Get-Command - Out-GridView" next steps?](https://www.experts-exchange.com/questions/27021522/PowerShell-Get-Command-Out-GridView-next-steps.html)