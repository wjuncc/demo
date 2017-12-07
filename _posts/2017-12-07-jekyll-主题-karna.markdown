---
layout: post
title:  "jekyll 主题 karna"
date:   2017-12-07 13:17:32 +0800
categories:  jekyll
tags:
    - jekyll 
---


### 小结 ###

1. 生成页面markdown的模板，要加个当前时间戳时分秒，  
因为用默认时间戳比如23:00:00， jekyll会默默做一件事，  
如果时间>系统时间,则不显示，实际上，是不导出html文件。  
不然很花时间。

2. 复制E:\n\wj\blog\demo\_site\assets\main.css
到 E:\n\wj\blog\demo\assets\main.css  
如果没有文件夹assets，就加一个文件夹assets    
注释掉  

		/*line-height: 54px;*/
		.site-nav {
		  float: right;
		  /*line-height: 54px;*/ }

### tag有问题 ###


在HUX blog 或者说 CLeanBLog中，tags的写法是：

	tags: - jekyll

相同的代码，复制到默认的jekyll3中    
上传到git后，在列表页面无法显示。  
用搜索也搜不出来。 

改成如下后正常。

	tags: jekyll 

这个错误其实是时间戳的问题。并非tag写错。 

#### 在本地测试 ####

报错：

	 Incremental build: disabled. Enable with --incremental
      Generating...
             Error: could not read file E:/n/wj/blog/demo/_posts/2017-12-07-karn
	a主题-jekyll.markdown: (<unknown>): block sequence entries are not allowed in th
	is context at line 6 column 7
	             Error: could not read file E:/n/wj/blog/demo/_posts/2017-12-07-去掉
	clover的自带标签.markdown: (<unknown>): could not find expected ':' while scanni
	ng a simple key at line 6 column 1
	                    done in 1.763 seconds.

具体是：  
> Error: could not read file (<unknown>): could not find expected ':' while scanning a simple key at line 6 column 1

跳过这个问题。  

### 报错2 ###

   	Regenerating: 1 file(s) changed at 2017-12-07 15:24:07              Error:could not read file E:/n/wj/blog/demo/_posts/2017-12-07-去掉clover的自带标签.markdown: (<unknown>): could not find expected ':' while scanning a simple key at line 6 column 1 
	...done in 1.135 seconds.

这是因为，头信息中的键值对，键+冒号+值中，冒号后面必须有空格，没有空格就报错。


### 报错4 ###

	 could not read file E:/n/wj/blog/demo/_posts/2017-12-07-去掉clover的自带标签.ma
	rkdown: (<unknown>): block sequence entries are not allowed in this context at line 6 column 7
	...done in 1.183 seconds.

### 报错5 ###

     Error: could not read file E:/n/wj/blog/demo/_posts/2017-12-06-用django搭建手机网站调用PC端指令.markdown: (<unknown>): found character that cannot start any token while scanning for the next token at line 7 column 1
    done in 1.443 seconds.

### 报错6 ###

	[2017-12-07 15:54:23] ERROR `/demo/django/2017/12/06/用django搭建手机网站调用PC端指令.html' not found.

这是因为。本地不能访问中文路径：

	http://127.0.0.1:4000/demo/django/2017/12/06/用django搭建手机网站调用PC端指令.html

下面可以：

	http://127.0.0.1:4000/demo/django/2017/12/06/%D3%C3django%B4%EE%BD%A8%CA%D6%BB%FA%CD%F8%D5%BE%B5%F7%D3%C3PC%B6%CB%D6%B8%C1%EE.html

上传git后可以访问中文路径。



下面列一些主题：

[mr-brown](http://jekyllthemes.org/themes/mr-brown/)  
[smart-material](http://jekyllthemes.org/themes/smart-material-theme/)
[google-grid-gallery](https://tympanus.net/codrops/2014/03/21/google-grid-gallery/)


[高端大气](http://jekyllthemes.org/themes/doc-theme/)
[很有特点](http://jekyllthemes.org/themes/doc-theme/)


# karna 主题  #

下载[karna](http://jekyllthemes.org/themes/karna/)  

报错：

	E:\n\wj\blog\karna-master\karna-master>jekyll serve -w --host=0.0.0.0
	Configuration file: E:/n/wj/blog/karna-master/karna-master/_config.yml
	  Dependency Error: Yikes! It looks like you don't have jekyll-seo-tag or one of
	 its dependencies installed. In order to use Jekyll as currently configured, you
	'll need to install this gem. The full error message from Ruby is: 'cannot load
	such file -- jekyll-seo-tag' If you run into trouble, you can find helpful resou
	rces at https://jekyllrb.com/help/!
	jekyll 3.6.2 | Error:  jekyll-seo-tag

安装gem：

	gem install jekyll-seo-tag


    Server address: http://0.0.0.0:4000/karna/

访问：

	http://127.0.0.1:4000/karna/

测试OK；  
这个css有问题，在拉小成手机后，再拉大，  
没有还原到大屏下的多个并列。  
而是单张图片左右撑满。


#### 参考 ####
* [karna](http://jekyllthemes.org/themes/karna/)  
