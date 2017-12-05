---
layout: post
title:  "[blog] 2. 用 jekyll 搭建blog222"
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


参考：

* [★★★★★GitHub Pages 静态博客 - 个人建站实录](http://alfred-sun.github.io/blog/2014/12/05/github-pages/)  这篇文章很过细，最后的细节是在这里解决的。
* [如何让jekyll服务可以在局域网中访问](http://www.jianshu.com/p/650b96306013)
* [windows7下安装ruby,rubyGems和devkit](http://blog.csdn.net/u012882134/article/details/51685127)
* [github上利用jekyll搭建自己的blog的操作顺序？](https://www.zhihu.com/question/30018945)
* [对这个 jekyll 博客主题的改版和重构](https://gaohaoyang.github.io/2016/03/12/jekyll-theme-version-2.0/)
* [Jekyll本地搭建开发环境以及Github部署流程](http://www.jianshu.com/p/f37a96f83d51)
