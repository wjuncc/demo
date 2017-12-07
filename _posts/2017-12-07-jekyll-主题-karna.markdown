---
layout: post
title:  "jekyll 主题 karna"
date:   2017-12-07 13:17:32 +0800
categories:  jekyll
tags:
    - jekyll 
    
--- 
## karna主题的最大问题 ##
本地测试：  
karna主题的css有问题，在拉小成手机后，再拉大，  
没有还原到大屏下的多个并列。  
而是单张图片左右撑满。  

在[demo](http://webjeda.com/karna/)会重现这个问题。

## 其他主题 ##

* 全部列表：[Jekyll Themes](http://jekyllthemes.org/page2/)  

* [Dopetrope](https://html5up.net/dopetrope)
* 干净[Clean](http://knaman2609.github.io/clean/)
* 很好展示了手机端和PC端[Dopetrope](http://jekyllthemes.org/themes/dopetrope/)
* 很商务，像微软：[Jekyll Doc Theme](http://jekyllthemes.org/themes/doc-theme/)  
* [很有特点]()


* 对圆角不感冒：[mr-brown](http://jekyllthemes.org/themes/mr-brown/)  
* 正正方方，不够好：[smart-material](http://jekyllthemes.org/themes/smart-material-theme/)
* 不如原版好[GridGallery](http://jekyllthemes.org/themes/gridgallery/)  
* 4年前，也不过时 [google-grid-gallery](https://tympanus.net/codrops/2014/03/21/google-grid-gallery/) -> [GridGallery](https://github.com/codrops/GridGallery)

* 动画切换花，不喜欢[ModernBlog](http://jekyllthemes.org/themes/modernblog/)
* 右边不要[Leonids](http://jekyllthemes.org/themes/leonids/)
* 大气有点装[Bef](http://artemsheludko.pw/bef/)


## 备忘录 ##
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


#### 参考 ####
* [karna](http://jekyllthemes.org/themes/karna/)  
