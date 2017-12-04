---
layout: post
title:  "[blog] 2. 用 jekyll 搭建blog（补问题）"
date:   2017-10-04 01:17:32 +0800
categories: jekyll update
tags: jekyll
--- 

## 1. 第1行  jekyll new . --force： ##

有的文章写作：

	jekyll demo

这样会创建一个文件夹demo，然后下一行写作

	cd demo

进入这个刚刚创建的文件夹。

我写作：

	jekyll new . --force

是在进入 demo 目录后创建，由于已经有git文件。
所以要加 --force，   

## 2. 第2行  jekyll serve： ##

有文章写作： 

	jekyll serve build --detach

在windows下面有问题。执行报错：(可能在linux和mac正常，未测试) 
	
	C:/Ruby24-x64/lib/ruby/gems/2.4.0/gems/jekyll-3.6.2/lib/jekyll/commands/serve.rb:180:in `fork': fork() function is unimplemented on this machine (NotImplementedError)
    from C:/Ruby24-x64/lib/ruby/gems/2.4.0/gems/jekyll-3.6.2/lib/jekyll/commands/serve.rb:180:in `boot_or_detach'


参考  [Spawn a background process in Ruby on Windows?](https://stackoverflow.com/questions/3840525/spawn-a-background-process-in-ruby-on-windows) 尝试解决： 
	
	gem install win32-process

仍旧报错，无法解决。

Hi - this has been reported before. I don't have access to a Windows machine to debug this, but I do belive that it is because MRI on Windows does not support fork. Either we need to add a note about this to the README (suggesting to use cygwin) or someone developing in Windows needs to supply a patch. I think spawn works not Windows but not fork. Could you open irb and just type fork and see if you get the same error please?

	
第3行：jekyll build

参考：

* [windows7下安装ruby,rubyGems和devkit](http://blog.csdn.net/u012882134/article/details/51685127)
* [github上利用jekyll搭建自己的blog的操作顺序？](https://www.zhihu.com/question/30018945)
* [对这个 jekyll 博客主题的改版和重构](https://gaohaoyang.github.io/2016/03/12/jekyll-theme-version-2.0/)
* [Jekyll本地搭建开发环境以及Github部署流程](http://www.jianshu.com/p/f37a96f83d51)

