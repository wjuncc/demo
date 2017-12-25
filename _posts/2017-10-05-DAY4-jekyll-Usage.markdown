---
layout: post
title:  "DAY4 jekyll Usage"
date:   2017-10-05 21:17:32 +0800
categories:  jekyll
tags: 
    - jekyll

---


## jekyll代码中显示2个大括号的问题 ##
react的代码有2个大括号，如\{\{，应该写作\\{\\{
错误举例：
```
Regenerating: 1 file(s) changed at 2017-12-26 02:29:36     Liquid Warning:
 Liquid syntax error (line 274): Expected end_of_string but found colon in "{{_h
tml: '<h1>Hello World!!</h1>'}}" in E:/n/wj/blog/demo/_posts/2017-10-14-react-js
-101-笔记3-2.markdown
```
参考[jekyll 下文章无法显示双大括号\{\{ \}\}和\{\% \%\}的处理](http://yukapril.com/2017/03/01/jekyll-brace.html)


## tag的问题 ##
1
```
tags: wtg  u盘
```
测试通过

2
```
tags: wtg
  u盘
```
测试不通过

3
```
tags: - jekyll
```
测试不通过

tags:  - jekyll 是推荐做法，为什么不通过？


今天偶然发现，在线上git，支持tag加杠的写法。
如，DAY4 修改jekyll主题 md 的写法：
 
tags: 
    - jekyll 
    - Hux 
	
线上支持。

尝试修改：

	tags: wtg  u盘
->
	
	tags: 
	    - wtg 
	    - u盘 


#### 参考 ####

* [使用`Jekyll`遇到的问题 · Issue #19 · mrdulin/blog · GitHub](https://github.com/mrdulin/blog/issues/19)
* [tags - jekyll推送到github之后tag插件分类页面显示404错误 - SegmentFault](https://segmentfault.com/q/1010000008719834)
* [Jekyll使用时遇到的各种小问题](http://hyq9508.github.io/jekyll/markdown/ruby/scss/2015/06/23/Jekyll-tips.html)
* [对这个 jekyll 博客主题的改版和重构](https://gaohaoyang.github.io/2016/03/12/jekyll-theme-version-2.0/)
* [使用Category标签隐藏Jekyll博客文章 - CSDN博客](http://blog.csdn.net/JireRen/article/details/52196249)
* [给GitHub Pages上的Jekyll站点添加标签支持 - Zero[Z.W.T] Blog](http://www.zerozwt.com/2017/08/28/add-tags-to-jekyll.html)
* [tags - Jekyll tag_gen plugin not working - Stack Overflow](https://stackoverflow.com/questions/14375331/jekyll-tag-gen-plugin-not-working)
* [please support tags without need plugins to make github pages support tags · Issue #867 · jekyll/jekyll · GitHub](https://github.com/jekyll/jekyll/issues/867)


## 时间的问题 ##
利用这一点，能隐藏自己还不想发布的博客页面，例如，`date`标签的年份改成1000年后，这样，页面就不会出现在博客列表中。 
 
jekyll根据系统时间，判断是否生成html。

	date:   2017-10-05 21:17:32 +0800

改成1000年后

	date:   3017-10-05 21:17:32 +0800

肯定不显示。

## jekyll中文路径 ##

<del>这个问题是jekyll2的，在jekyll3下没有了。 </del>  
这个问题是ruby的问题，不是jekyll版本的问题。  
文件名是中文的，用localhost访问，有的页面404，有的页面正常。正常的页面一直正常，404的页面一直404。
例如，第1组页面正常：
```
2017-11-09 React动画指南(1)常规写法
```
第2组页面404：
```
2017-11-10 React动画指南(2)复用写法
2017-11-11 React动画指南(3)项目实战
```

这个问题，

1. 远程git上的jekyll支持中文。 
2. 只是本地localhost或者192.168.1.X 有问题，

### 解决思路 ###

1. 通过修改rb文件，来使得ruby服务器能正常访问中文路径。
2. 把文件名翻译成汉语拼音。是一个思路，但是不实用。这样做，会造成listary或者everthing搜索不方便。

能够用中文，还是用中文好。垂直映射比水平转化要少一层壳，更利于搜索。

### 解决办法 ###

路径：
C:\Ruby24-x64\lib\ruby\2.4.0\webrick\httpservlet

修改安装目录\Ruby22-x64\lib\ruby\2.2.0\webrick\httpservlet下的filehandler.rb文件，建议先备份。

找到下列两处，添加一句（ + 的一行为添加部分）

```ruby
	path = req.path_info.dup.force_encoding(Encoding.find("filesystem"))
	+ path.force_encoding("UTF-8") # 加入编码
```
```ruby
	if trailing_pathsep?(req.path_info)
	break if base == "/"
	+ base.force_encoding("UTF-8") # 加入編碼
	break unless File.directory?(File.expand_path(res.filename + base))
```
然后重启服务器即可jekyll clean && jekyll s


#### 参考 ####

* [jekyll如何使用中文路径](http://blog.laofu.online/2017/08/06/jekyll-cn-path/)
* [jekyll serve 无法本地预览 中文路径问题 解决](https://rawbin-.github.io/开发技术/2015/06/13/jekyll-serve/)
* [Jekyll编译中文文件名的网页的本地预览问题。](http://www.oschina.net/question/1396651_132154)
* [jekyll中文文件名本地预览问题](http://kael-aiur.com/入门指引/jekyll中文文件名本地预览问题.html) 
* [jekyll支持中文解决办法 - 单客哦朋 - thxopen.com](http://www.thxopen.com/jekyll/2014/04/17/jekyll-able-gbk.html)