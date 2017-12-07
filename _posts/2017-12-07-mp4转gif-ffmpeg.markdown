---
layout: post
title:  "mp4转gif ffmpeg"
date:   2017-12-07 22:52:41 +0800
categories:  
tags: 
---

# mp4转gif ffmpeg #


## win7 命令行 ##

	ffmpeg -t 13.6 -ss 00:00:01 -i CVZK3966.MP4 CVZK3966.gif

	ffmpeg -ss 00:00:01 -i CVZK3966.MP4 CVZK3966.gif

定义帧率 16fps:

	ffmpeg -i CVZK3966.MP4 -r 16 -filter:v "setpts=0.125*PTS" -an output-16.gif

定义帧率 32fps:

	ffmpeg -i CVZK3966.MP4 -r 32 -filter:v "setpts=0.125*PTS" -an output-32.gif

定义帧率 32fps+缩放视频尺寸:

	ffmpeg -i output-32.gif -vf scale=320:-1  -r 32 -filter:v "setpts=0.125*PTS" -an output-32-320.gif


失败

在前面32fps的基础上，缩放视频尺寸

	ffmpeg -i output-32.gif -vf scale=320:-1 output-32-320.gif

	ffmpeg -i output-32.gif -vf scale=160:-1 output-32-160.gif


#### -vf ####

-vf意思是


### 压缩gif ###

gifsicle


	convert test.gif -fuzz 15% -layers Optimize result.gif


## 2 ubuntu14.04 ##
ubuntu打开命令行：Ctrl+Alt+T  
ubuntu打开命令行标签页：Ctrl+Shit+T 
### 安装1 ### 

	sudo apt-get install ffmpeg

报错：

	sudo apt-get install ffmpeg
	正在读取软件包列表... 完成
	正在分析软件包的依赖关系树       
	正在读取状态信息... 完成       
	现在没有可用的软件包 ffmpeg，但是它被其它的软件包引用了。
	这可能意味着这个缺失的软件包可能已被废弃，
	或者只能在其他发布源中找到


### 安装2

通过PPA安装FFmpeg 2.5.1 

	sudo add-apt-repository ppa:kirillshkrogalev/ffmpeg-next
	sudo apt-get update
	sudo apt-get install ffmpeg



### 使用 ###

	ffmpeg -t 3.6 -ss 00:00:01 -i Screencast_2016-01-13-17-01-38.mp4  small-clip.gif


	注释：3.6是秒数，00:00:01是开始时间。 

### 实例 ###
CVZK3966.MP4

	ffmpeg -t 3.6 -ss 00:00:01 -i CVZK3966.MP4 CVZK3966.gif



#### 参考 ####

* [使用 ffmpeg 实现 MP4 与 GIF 的互转 - 任平生的学习笔记](http://note.rpsh.net/posts/2015/04/21/mac-osx-ffmpeg-mp4-gif-convert/)
* [压缩gif的正确姿势](https://segmentfault.com/a/1190000000436384)
* [ffmpeg参数解释](http://blog.csdn.net/hemingwang0902/article/details/4382205)
* [linux下使用 ffmpeg 实现MP4转gif - CSDN博客](http://blog.csdn.net/weizongwei5/article/details/50514105)
* [使用ffmpeg来将mp4视频转换成gif格式图片 - CSDN博客](http://blog.csdn.net/lj402159806/article/details/54837637)
* [ffmpeg转换GIF图片参数 - 楚盟博客](https://www.5yun.org/9385.html)
* [linux下使用 ffmpeg 实现MP4转gif - 程序园](http://www.voidcn.com/article/p-dtpymbgq-xn.html)
* [制作更好的 GIF: 另一种更好的办法 · Phoenix's island](https://blog.phoenixlzx.com/2014/03/25/yet-anothor-better-gif-method/)
* [FFmpeg实用命令：音频、视频格式转换和其它操作 – WTF Daily Blog](http://blog.topspeedsnail.com/archives/1699)
* [使用 ffmpeg 实现 MP4 与 GIF 的互转 · Issue #95 · ameizi/DevArticles · GitHub](https://github.com/ameizi/DevArticles/issues/95)
* [How do I convert a video to GIF using ffmpeg, with reasonable quality? - Super User](https://superuser.com/questions/556029/how-do-i-convert-a-video-to-gif-using-ffmpeg-with-reasonable-quality)