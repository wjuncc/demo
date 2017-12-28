---
layout: post
title:  "获取Chrome浏览器地址栏URL"
date:   2015-02-04 20:01:32 +0800
categories: 
tags: 
    - powershell

---


## 1  操作 inspect.exe ##


使用 inspect.exe ， 设置 UI Automation 模式。   
chrome浏览器的URL地址信息，在 Value Value 里面。  
Inspect.exe 树结构 pyautowin

在没有树形窗口，不知道为什么。 



## 2 uiautomation 比 pyautowin 强 ##


### 获取 chrome 地址栏的值 ###

获取 EditControl 的值（在 inspect.exe）

* Value.Value
* LegacyIAccessible.Value

实际调用

* edit.CurrentValue()






---------------------------------------------

## 下面不重要了 ##

当前版本 winauto 0.6.2


注意，2个平台  

* Win32 API (backend="win32") - a default backend for now
MFC, VB6, VCL, simple WinForms controls and most of the old legacy apps
* MS UI Automation (backend="uia")
WinForms, WPF, Store apps, Qt5, browsers


Delphi 获取Chrome浏览器地址栏URL  

	var hChrome:hwnd; addr: array[0..255] of char; 
	begin hChrome:=FindWindow('Chrome_WidgetWin_1',nil); 
	hChrome:=FindWindowEx(0,hChrome,'Chrome_WidgetWin_1',nil); 
	hChrome:=FindWindowEx(hChrome,0,'Chrome_OmniboxView',nil); 
	SendMessage(hChrome,wm_gettext,256,Integer(@addr)); 
	Mmo1.Lines.Add(addr); end;
	
python 获取Chrome浏览器地址栏URL  

	self.ChromeUrl = self.app["Chrome_WidgetWin_1"]["Chrome_OmniboxView"]

### 报错 ###

	pywinauto.findbestmatch.MatchError: Could not find 'Chrome_OmniboxView' in '[u'Chrome Legacy Window', u'Chrome_RenderWidgetHostHWND', u'Chrome Legacy WindowChrome_RenderWidgetHostHWND']'

	pywinauto.findbestmatch.MatchError: Could not find 'main' in '[u'', 'Button16', 'Button15', 'Button14', 'Button13', 'Button12', 'Button11', 'Button10', 'Button18', u'\u5173\u95edButton1', u'\u5173\u95 ... (truncated)

	pywinauto.findbestmatch.MatchError: Could not find 'main' in '[u'', u'Chrome', u'\u5728\u4e2d\u6587windows\u4e0b\u4f7f\u7528pywinauto\u8fdb\u884c\u7a97\u53e3\u64cd\u4f5c\uff08\u4e00\uff09 - kevin\u768 ... (truncated)

执行同样的程序，但是报错是3个不同的错误，  
这说明，是动态获取的，


在Mac上：

	 from appscript import *
	>>> map(lambda x: x.title(), app('Google Chrome').windows[0].tabs())
	[u'Stack Overflow', u'Google']

On Windows, you will want to look into OLE Automation with Python.

参考： 


* [Delphi 获取Chrome浏览器地址栏URL](https://my.oschina.net/u/582827/blog/887539)
* [实时获取浏览器的地址栏的网页地址](http://blog.csdn.net/jiangqin115/article/details/47731813)
* [pywinauto帮助文档](http://pywinauto.readthedocs.io/en/latest/getting_started.html)
* [How to get the current URL from Chrome using pywinauto 0.6](https://stackoverflow.com/questions/46145284/how-to-get-the-current-url-from-chrome-using-pywinauto-0-6)
* [get_info_from_app](https://github.com/LevikovCollector/Diplom-EventCollector/blob/54541962036549adf037fc8f6c86d804048f22c1/get_info_from_app.py)
* [caterpillar](https://github.com/chromium/caterpillar/blob/985419af32f9bbd3abc934db3edc09523477118a/src/caterpillar.py)
* [List of open browser tabs programmatically](https://stackoverflow.com/questions/7537832/list-of-open-browser-tabs-programmatically)
* [http://gracegreat1.me/2017/11/为自己的博客添加搜索引擎-Google-收录-以-Namecheap-为例/](http://gracegreat1.me/2017/11/为自己的博客添加搜索引擎-Google-收录-以-Namecheap-为例/)
* [uiautomation](https://pypi.python.org/pypi/uiautomation)
* [Python-UIAutomation-for-Windows](https://github.com/yinkaisheng/Python-UIAutomation-for-Windows)
* [SWAPY](https://github.com/pywinauto/SWAPY)
* [开源自己用python封装的一个Windows GUI(UI Automation)自动化工具，支持MFC,Windows Forms,WPF,Metro,Qt](http://www.cnblogs.com/Yinkaisheng/p/3444132.html)
* [用开源uiautomation自动化操作火狐](https://zhuanlan.zhihu.com/p/30409594)
* [Windows UI自动化测试的XPATH实现 - WPATH](https://segmentfault.com/a/1190000010339021)
* [使用uiautomation自动化重命名pdf书签，使全大写字母变成首字母大写](http://www.cnblogs.com/Yinkaisheng/p/4820954.html)   
