---
layout: post
title:  "mp4转gif ffmpeg"
date:   2017-12-07 22:52:41 +0800
categories:  public
tags: gif ffmpeg
---

# 步骤 #

## 1 裁剪mp4前后帧
【版本】Boilsoft Video Splitter 6.34.4  
【备要】 
uVideoSplitter.py
调用
VideoSplitterBat.py
调用
VideoSplitter loader.exe

注意：
处理后文件名有变化：  
CVZK3966.MP4 ->
CVZK3966.m4v


## 2 mp4转gif 
【版本】ffmpeg version 3.4 Copyright (c) 2000-2017 the FFmpeg developers
  built with gcc 7.2.0 (GCC)

【备要】 
m4v转gif.bat

	%~d0
	cd %cd%  
	::定义帧率 32fps:
	ffmpeg -i CVZK3966.m4v -r 32 -filter:v "setpts=0.125*PTS" -an CVZK3966-32.gif
	::在前面32fps的基础上，缩放视频尺寸
	ffmpeg -i CVZK3966-32.gif -vf scale=320:-1 CVZK3966-32-320.gif
	
## 3 压缩gif ##
【版本】  ImageMagick 7.0.7 Q16 (64-bit)  
【备要】 

1. 添加系统环境变量  
添加当前路径到系统环境变量.bat  
  
C:\Program Files\ImageMagick-7.0.7-Q16

压缩gif.bat

	cd 
	convert test.gif -fuzz 5% -layers Optimize result.gif




~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### 备忘录 ###
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

错误，或许是没科学上网。

	E: 软件包 ffmpeg 没有可供安装的候选者
	wj@wj-System-Product-Name:~/blog$ ffmpeg
	ffmpeg：未找到命令
	wj@wj-System-Product-Name:~/blog$ sudo add-apt-repository ppa:kirillshkrogalev/ffmpeg-next
	 This PPA provides backported release ffmpeg for current releases Ubuntu (Trusty, Utopic, etc.)
	 更多信息： https://launchpad.net/~kirillshkrogalev/+archive/ubuntu/ffmpeg-next
	按回车继续或者 Ctrl+c 取消添加


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