---
layout: 	post
title: 	 	"jekyll Hux主题修改"
subtitle:   ""
date:   	2017-12-06 21:17:32 +0800
author:     "wj"
header-img: "img/post-bg.jpg"
categories:  
tags: 
    - jekyll 
---

### jekyll ###
找主题，找到
### CleanBlog ###
[很不错，同步新的+官方](https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll)

本来是准备上CleanBlog的，但是

### Hux blog ###
Hux blog 就是 CleanBlog+中文优化

下载后[Hux blog](https://github.com/Huxpro/huxpro.github.io/blob/master/README.zh.md#environment)后执行____start___server.bat

	%~d0
	cd %cd%
	cd huxpro.github.io-master
	::默认本机访问
	::jekyll serve
	::在局域网访问
	jekyll serve -w --host=0.0.0.0

报错：

	E:\n\wj\blog\huxpro.github.io-master>jekyll serve -w --host=0.0.0.0
	Configuration file: none
	            Source: E:/n/wj/blog/huxpro.github.io-master
	       Destination: E:/n/wj/blog/huxpro.github.io-master/_site
	 Incremental build: disabled. Enable with --incremental
	      Generating...
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-08-16-miui6.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-09-04-is-pure-android-better.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-10-01-why-alibaba-ux-sucks.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-11-20-responsive-web-design.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-12-13-wechat-block-kuaidi.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	14-01-29-hello-2015.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-03-10-apple-event-2015.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-03-25-digital-native.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-03-31-e2e_user_scenarios.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-04-14-unix-linux-note.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-04-15-os-metro.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-05-11-see-u-ali.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-05-25-js-module-loader.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-06-15-alitrip-strategy.markdown does not exist.
	     Build Warning: Layout 'keynote' requested in huxpro.github.io-master/_posts
	/2015-07-09-js-module-7day.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-09-22-js-version.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-10-28-how-designer-learn-fe.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	15-12-15-ios9-safari-web.markdown does not exist.
	     Build Warning: Layout 'keynote' requested in huxpro.github.io-master/_posts
	/2015-12-28-css-sucks-2015.markdown does not exist.
	    Liquid Warning: Liquid syntax error (line 148): Unexpected character # in "{
	{# each}}" in E:/n/wj/blog/huxpro.github.io-master/huxpro.github.io-master/_post
	s/2016-02-01-React-vs-Angular2.markdown
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	16-02-01-React-vs-Angular2.markdown does not exist.
	     Build Warning: Layout 'keynote' requested in huxpro.github.io-master/_posts
	/2016-06-05-pwa-in-my-pov.markdown does not exist.
	     Build Warning: Layout 'keynote' requested in huxpro.github.io-master/_posts
	/2016-10-20-pwa-qcon2016.markdown does not exist.
	     Build Warning: Layout 'keynote' requested in huxpro.github.io-master/_posts
	/2016-11-20-sw-101-gdgdf.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	17-02-09-nextgen-web-pwa.markdown does not exist.
	     Build Warning: Layout 'post' requested in huxpro.github.io-master/_posts/20
	17-06-25-you-are-slaves.markdown does not exist.
	  Liquid Exception: Could not locate the included file 'posts/2017-07-12-upgradi
	ng-eleme-to-pwa/zh.md' in any of ["E:/n/wj/blog/huxpro.github.io-master/_include
	s"]. Ensure it exists in one of those directories and, if it is a symlink, does
	not point outside your site source. in E:/n/wj/blog/huxpro.github.io-master/huxp
	ro.github.io-master/_posts/2017-07-12-upgrading-eleme-to-pwa.markdown
	jekyll 3.6.2 | Error:  Could not locate the included file 'posts/2017-07-12-upgr
	ading-eleme-to-pwa/zh.md' in any of ["E:/n/wj/blog/huxpro.github.io-master/_incl
	udes"]. Ensure it exists in one of those directories and, if it is a symlink, do
	es not point outside your site source.
	
	E:\n\wj\blog\huxpro.github.io-master>


	Liquid Exception: Could not locate the included file 'posts/2017-07-12-upgradi
	ng-eleme-to-pwa/zh.md' in any of ["E:/n/wj/blog/huxpro.github.io-master/_include
	s"]. Ensure it exists in one of those directories and, if it is a symlink, does
	not point outside your site source. in E:/n/wj/blog/huxpro.github.io-master/huxp
	ro.github.io-master/_posts/2017-07-12-upgrading-eleme-to-pwa.markdown

这是一个路径问题，必须在命令行进当前路径。
	
	cd XXX

修改后，报错：

	E:\n\wj\blog\huxpro.github.io-master\huxpro.github.io-master>jekyll serve -w --h
	ost=0.0.0.0
	Configuration file: E:/n/wj/blog/huxpro.github.io-master/huxpro.github.io-master
	/_config.yml
	       Deprecation: The 'gems' configuration option has been renamed to 'plugins
	'. Please update your config file accordingly.
	  Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one o
	f its dependencies installed. In order to use Jekyll as currently configured, yo
	u'll need to install this gem. The full error message from Ruby is: 'cannot load
	 such file -- jekyll-paginate' If you run into trouble, you can find helpful res
	ources at https://jekyllrb.com/help/!
	jekyll 3.6.2 | Error:  jekyll-paginate
	
	E:\n\wj\blog\huxpro.github.io-master\huxpro.github.io-master>
	
Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one o
f its dependencies installed. In order to use Jekyll as currently configured, yo
u'll need to install this gem. The full error message from Ruby is: 'cannot load
 such file -- jekyll-paginate' If you run into trouble, you can find helpful res
ources at https://jekyllrb.com/help/!
jekyll 3.6.2 | Error:  jekyll-paginate

在 Jekyll 3 中，需要在 gems 中安装 jekyll-paginate 插件，并添加到你的 Gemfile 和 _config.yml 中。在 Jekyll 2 中，分页是标准功能。

	gem install jekyll-paginate

测试OK，默认就是Huxpro写的博客内容，但是，

### 如何得到纯净版？ ###

> 大家可以直接fork模板——huxblog-boilerplate
> 
>
	git clone git@github.com:Huxpro/huxblog-boilerplate.git

报错：

	PS C:\Users\Administrator> cd E:\n\wj\blog\huxpro.github.io-master
	PS E:\n\wj\blog\huxpro.github.io-master> git clone git@github.com:Huxpro/huxblog-boilerplate.git
	Cloning into 'huxblog-boilerplate'...
	The authenticity of host 'github.com (192.30.255.112)' can't be established.
	RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
	Are you sure you want to continue connecting (yes/no)? yes
	Warning: Permanently added 'github.com,192.30.255.112' (RSA) to the list of known hosts.
	Permission denied (publickey).
	fatal: Could not read from remote repository.
	
	Please make sure you have the correct access rights
	and the repository exists.
	PS E:\n\wj\blog\huxpro.github.io-master>

可能要用SSL模式。  
从[这里](https://github.com/Huxpro/huxblog-boilerplate)下载zip包

bat改一改：

	%~d0
	cd %cd%
	cd huxblog-boilerplate-master
	::默认本机访问
	::jekyll serve
	::在局域网访问
	jekyll serve -w --host=0.0.0.0

测试OK

### 改日期不显示 ###

必须在系统时间之前，  
例如

	date:   	2017-12-06 21:17:32 +0800

如果改成100年后

	date:   	3017-12-06 21:17:32 +0800
	
肯定不显示。

### 字体太小了 ###

less/hux-blog.less 看到

	body {
		.sans-serif;
		font-size: 26px;
		// Hux mpdify to 16px (Mobile First), and increase to 20px while 768+ width
		color: @gray-dark;
		//-webkit-user-select:text; //对于 Blog 还是先不开启这句。
		overflow-x : hidden;
	}

> Hux mpdify to 16px (Mobile First)
> Hus修改到16像素（手机端优先）

只说了一句，但是不知道具体是哪段改的，怎么改的，是JS还是Less？

用python遍历，看到：



代码看不清楚

### 映射的文件是index.html ###
默认的jekyll，生成->  文件名.html，  
CleanBLog，   生成->   文件名/index.html.  
估计是CleanBLog的问题。

(完)


#### 参考 ####

* [BlackrockDigital/startbootstrap-clean-blog-jekyll: A Jekyll version of the Clean Blog theme by Start Bootstrap](https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll)
* [Hello 2015](http://huangxuan.me/2015/01/29/hello-2015/)
* [CleanBlog(个人博客+源码) - luoxn28 - 博客园](https://www.cnblogs.com/luoxn28/p/5597385.html)
* [Clean Blog – Laravel学院](http://laravelacademy.org/tags/clean-blog)
* [博客系列 – Laravel学院](http://laravelacademy.org/tutorials/blog)
* [Clean Blog主题 - Drupal中文网](http://www.drupalc.com/article/clean-blog-theme-393)
* [Django cms 教程十一：设置头部动态效果 - 蜗牛博客- 三根K线改三观](http://www.snailtoday.com/archives/7870)
* [详解在 Angular 项目中添加 clean-blog 模板_AngularJS_脚本之家](http://m.jb51.net/article/117746.htm)
* [Hello, this is my new theme of blog - YuanFu’s blog - MrFu blog](https://mrfu.me/life/2015/07/19/the_new_blog_theme/)
* [Codeboy Blog的搭建 - CSDN博客](http://blog.csdn.net/dliyuedong/article/details/47439721)
* [从零开始折腾Jekyll - Biu^Biu's Blog](http://bluebiu.com/blog/learn-to-use-jekyll.html)



#### 参考 ####
2年前或者1年前的，可能和现在的版本3有冲突：

* [全部列表-Jekyll Themes](http://jekyllthemes.org/page2/)
* [Liberxue/liberxue.github.io: Liberxue blog for Jekyll themes 轻量级自适应 简洁 卡片式博客主题 3秒搞定GitHub blog](https://github.com/Liberxue/liberxue.github.io)
* [joytou/joytou.github.io: JOYTOU](https://github.com/joytou/joytou.github.io#cn)
* [不是很美：JOYTOU - 一个热爱折腾、不肯休息的业余程序员！](https://joytou.github.io/cn/)
* [不喜欢黑白的：Simpleyyt/jekyll-theme-next: Elegant theme for Jekyll.](https://github.com/Simpleyyt/jekyll-theme-next)
* [正文在右边，要在左边：suyan/suyan.github.io: My Blog.](https://github.com/suyan/suyan.github.io)
* [很久没有更新了：SimpleGray/README.md at master · mytharcher/SimpleGray](https://github.com/mytharcher/SimpleGray/blob/master/README.md)
* [很久没有更新了：Huxpro/huxpro.github.io: My Blog / Jekyll Themes / PWA](https://github.com/Huxpro/huxpro.github.io)
* [很久没有更新了：gansteed/gansteed.github.io](https://github.com/gansteed/gansteed.github.io)