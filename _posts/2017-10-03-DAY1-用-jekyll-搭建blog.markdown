---
layout: post
title:  "DAY1 用 jekyll 搭建blog"
date:   2017-10-03 01:17:32 +0800
categories: jekyll update
tags: jekyll
---


## 1. 安装ruby插件jekyll。  ##

jekyll，需要ruby和RubyGems。 

windows下，使用rubyinstaller-2.4.2-2-x64.exe安装的ruby，本身就带RubyGems。

其实只用安装jekyll 

	gem install jekyll 


## 2. 在命令行运行jekyll。  ##

下面3行，分别是：
* 创建，
* 启动服务，
* 构建

	jekyll new . --force
	jekyll serve
	jekyll build
	bundle exec jekyll serve
	
## 3. 在http://127.0.0.1:4000/访问 ##

启动后，手工打开 [http://127.0.0.1:4000/](http://127.0.0.1:4000/)   
这是一个固定的地址、  
这里有一些问题，单独拎出来讲。

## 4. 在局域网访问  ##

	jekyll serve -w --host=0.0.0.0
	
	http://192.168.1.6:4000/demo/

## 5. 修改页面文件 ##
只用动一个文件夹：_posts  
jekyll 会自动更新

## 6. 上传git后，发现文件路径不对 ##
首先是assets/main.css没有.  
其次是点击首页的连接。本来是：

	https://wjuncc.github.io/demo/jekyll/update/2017/12/04/test.html 

实际是

	https://wjuncc.github.io/jekyll/update/2017/12/04/test.html

路径问题，只用改一个地方：

_config.yml （确保本地与 GitHub Pages URL 路径一致） 

	baseurl: /demo

（完）

### 备忘录 ###
网站模板，是解压后，直接启动。  
这样分开，好找问题。  
而不用jekyll3创建后，覆盖，再启动。
因为有些模板没有更新，还是jekyll2.

从[jekyll](http://jekyllthemes.org/)下载网站模板
	比如 [progress](http://jekyllthemes.org/themes/progress-for-jekyll/)

	把里面的内容解压到你自己的网站目录底下。


	报错

       	Deprecation: The 'gems' configuration option has been renamed to 'plugins'. Please update your config file accordingly.

	配置文件_config.yml中，使用了 plugins 的配置项，应该是用plugins替换掉gems。

	报错

		  Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one o
		f its dependencies installed. In order to use Jekyll as currently configured, yo
		u'll need to install this gem. The full error message from Ruby is: 'cannot load
		 such file -- jekyll-paginate' If you run into trouble, you can find helpful res
		ources at https://jekyllrb.com/help/!
		jekyll 3.6.2 | Error:  jekyll-paginate


	报错

		>jekyll serve
		C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/core_ext/kernel_require.rb:55:in `require'
		: cannot load such file -- bundler (LoadError)
		        from C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/core_ext/kernel_require.rb:55


	Try running:

		$ gem install bundler
		$ bundle install
		$ bundle exec jekyll serve**

#### 参考： ####

* [★★★★★GitHub Pages 静态博客 - 个人建站实录](http://alfred-sun.github.io/blog/2014/12/05/github-pages/)  这篇文章很过细，最后的细节是在这里解决的。
* [如何让jekyll服务可以在局域网中访问](http://www.jianshu.com/p/650b96306013)
* [windows7下安装ruby,rubyGems和devkit](http://blog.csdn.net/u012882134/article/details/51685127)
* [github上利用jekyll搭建自己的blog的操作顺序？](https://www.zhihu.com/question/30018945)
* [对这个 jekyll 博客主题的改版和重构](https://gaohaoyang.github.io/2016/03/12/jekyll-theme-version-2.0/)
* [Jekyll本地搭建开发环境以及Github部署流程](http://www.jianshu.com/p/f37a96f83d51)
* [Github Pages + Jekyll 独立博客一小时快速搭建&上线指南](http://playingfingers.com/2016/03/26/build-a-blog/)
* [这个Blog网站的搭建过程](http://www.vanbein.com/posts/jekyll/2016/03/09/blog/)
* [Github使用jekyll建站过程踩过的坑](http://yufenghe.github.io/web-build/2016/04/14/my-github-problem.html)
* [Jekyll搭建写作环境问题集锦](www.jianshu.com/p/12e7e1f8007e)
* [将纯文本转换为静态博客网站](http://jekyllcn.com/docs/home/)
* [Github Pages + Jekyll 独立博客一小时快速搭建&上线指南](playingfingers.com/2016/03/26/build-a-blog)
* [Jekyll 教程-2017](http://wiki.jikexueyuan.com/project/jekyll/quickstart.html)
* [github上利用jekyll搭建自己的blog的操作顺序？](https://www.zhihu.com/question/30018945)
* [Jekyll和Github搭建个人静态博客--2016](http://pwnny.cn/original/2016/06/26/MakeBlog.html)
* [使用jekyll和hexo搭建免费博客 2016-05-20  ](http://www.alonemonkey.com/2016/05/20/blog-by-jekyll-hexo/)
* [一步步在GitHub上创建博客主页-最新版-2014](http://www.pchou.info/ssgithubPage/2014-07-04-build-github-blog-page-08.html)
* [一步步在GitHub上创建博客主页](http://www.pchou.info/ssgithubPage/2013-01-03-build-github-blog-page-01.html)
* [建一个免费的，无限流量的Blog----github Pages和Jekyll入门-- 2012年8月25日](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)
* [模板](http://jekyllthemes.org/)
