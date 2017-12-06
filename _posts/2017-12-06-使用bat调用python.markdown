---
layout: post
title:  "使用bat调用python"
date:   2017-12-06 21:17:32 +0800
categories:  
tags: cmd
---

# 使用bat调用python #

右键菜单调用bat，bat再调用pyhon，  
例如重启命令RebootWin7.bat：
	
	@echo off
	%~d0
	cd %cd% 
	pythonw RebootWin7.py


只在RebootWin7.py同一目录有效果。  
在其他目录下调用，都没有效果。    
这是因为，使用右键菜单时。右键菜单会把目录传给bat。     
bat中的 %cd% 即当右键菜单目录，  
而不是RebootWin7.py所在目录。

有2种解决方案：  

1. 改成绝对路径：

		@echo off
		C:
		cd C:\Python27\Lib\site-packages\wj7\plugin\rightmenu\bin
		pythonw RebootWin7.py
2. 把RebootWin7.py文件所在目录加到系统环境变量

现在用绝对路径方案，第2种未测试。

#### 参考 ####

* [bat脚本调用python - CSDN博客](http://blog.csdn.net/jdzfjfhnui/article/details/50126529)
* [Bat执行Python脚本的问题 - CSDN博客](http://blog.csdn.net/tp7309/article/details/76737660)
* [bat批处理执行python - CSDN博客](http://blog.csdn.net/shy871265996/article/details/17246981)
* [windows下使用批处理文件调用python程序 - harrychinese - 博客园](http://www.cnblogs.com/harrychinese/p/call_python_cli_in_batch_script.html)
* [windows下使用批处理文件调用python程序](https://www.bbsmax.com/A/KE5QEA845L/)
* [windows下使用批处理文件调用python程序 - 相关文章](https://www.bbsmax.com/R/KE5QEA845L/)
* [用.bat批處理執行Python程序心得-好寂寞先生-51CTO博客](http://blog.51cto.com/pannyhjm/1154666)
* [批处理中运行python程序 并传入n个参数，怎么写。_百度知道](https://zhidao.baidu.com/question/518929003200927285.html)
* [bat调用python脚本 - 编程资料之家](http://echo.logphp.com/list/YmF06LCD55SocHl0aG9u6ISa5pys.html)
* [Windows使用bat批处理执行python程序 - CSDN博客 - 钱柜娱乐开户](http://www.tk4479.net/hjulkk/article/details/52549674)
* [搜索结果_bat 调用python脚本](https://zhidao.baidu.com/index?word=bat+调用python脚本&ri=3&from=qb&ssid=&uid=bd_1424530026_403&pu=sz%40224_240%2Cos%40&step=6&bd_page_type=1&init=middle)
* [BAT调用python大法【bat吧】_百度贴吧](http://tieba.baidu.com/p/4868267988)