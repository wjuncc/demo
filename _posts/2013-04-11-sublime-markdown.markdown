---
layout: post
title:  "sublimeText3安装markdown插件"
date:   2013-04-11 01:17:32 +0800
categories: sublime
cats: sublimeText3

---

## sublimeText3安装markdown插件 ##

windows上最好用的markdown软件，据传说是markdownPad。   
linux下的markdown软件，感觉极不好用。字体大小不能调整。。。  

先在windows上热身。  
再到Linux下使用。  



### 安装 ###

选择时候的前缀是 omni  
注意，安装 OmniMarkupPreviewer 而不是 Markdown Preveiw

会打开chrome浏览器窗口。
例如：

	http://127.0.0.1:51004/view/50

就是说：  
使用的时候，要2个窗口并排打开，  
左边是Sublime，右边是chrome。  
修改左边的内容，会实时刷新右边的内容。

有2个问题：

1. 由于它使用了端口，所以说，会和科学上网冲突。  
	一旦科学上网，这个就是404了。 
2. 在ubuntu上，未见得能2个窗口并排显示。 

### Markdown Preveiw 的做法
而 Markdown Preveiw 插件，是直接导出一个html文件在C盘，

	file:///C:/users/admini~1/appdata/local/temp/17.html

### 下面不再重要 ###

### 使用 ###
Set Syntax: Markdown
Markdown Preveiw: preveiw in browser

### 遗留问题
3. sublime的markdown只能导出html，不能导出pdf。

###### 参考 ######

* [介绍Sublime3下两款Markdown插件 - 简书](http://www.jianshu.com/p/335b7d1be39e)
* [Sublime Text3下的markdown插件的安装及配置 - Sinte-Beuve - 博客园](http://www.cnblogs.com/Sinte-Beuve/p/5148108.html)
* [在 Sublime 中配置 Markdown 环境 - Blog of 太极儒](http://frank19900731.github.io/blog/2015/04/13/zai-sublime-zhong-pei-zhi-markdown-huan-jing/)
* [Sublime Text 3 Markdown 写作设置 - jdhao's blog](https://jdhao.github.io/2017/03/04/Sublime-Windows-Markdown/)
* [近乎完美的 Markdown 写作体验 - Sublime Text 3 + OmniMarkupPreviewer](http://macplay.leanote.com/post/近乎完美的-Markdown-写作体验-Sublime-Text-3-OmniMarkupPreviewer)
* [分享-介绍Sublime3下两款Markdown插件](https://linux.cn/article-5965-1.html)
* [Sublime Text 2中如何实现Markdown语法高亮？如何实现实时双窗口预览? - 知乎](https://www.zhihu.com/question/20712067)
* [sublime安装markdown插件 - CSDN博客](http://blog.csdn.net/ababybear/article/details/51512125)
* [使用Sublime Text 3写Markdown - CSDN博客](http://blog.csdn.net/qazxswed807/article/details/51235792)