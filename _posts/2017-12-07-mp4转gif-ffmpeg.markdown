---
layout: post
title:  "mp4转gif ffmpeg"
date:   2017-12-07 22:52:41 +0800
categories:  
tags: 
---

# mp4转gif ffmpeg #

### 安装 ### 

	sudo apt-get install ffmpeg

### 使用 ###

	ffmpeg -t 3.6 -ss 00:00:01 -i Screencast_2016-01-13-17-01-38.mp4  small-c


	注释：3.6是秒数，00:00:01是开始时间。 



#### 参考 ####

* [使用 ffmpeg 实现 MP4 与 GIF 的互转 - 任平生的学习笔记](http://note.rpsh.net/posts/2015/04/21/mac-osx-ffmpeg-mp4-gif-convert/)
* [linux下使用 ffmpeg 实现MP4转gif - CSDN博客](http://blog.csdn.net/weizongwei5/article/details/50514105)
* [使用ffmpeg来将mp4视频转换成gif格式图片 - CSDN博客](http://blog.csdn.net/lj402159806/article/details/54837637)
* [ffmpeg转换GIF图片参数 - 楚盟博客](https://www.5yun.org/9385.html)
* [linux下使用 ffmpeg 实现MP4转gif - 程序园](http://www.voidcn.com/article/p-dtpymbgq-xn.html)
* [制作更好的 GIF: 另一种更好的办法 · Phoenix's island](https://blog.phoenixlzx.com/2014/03/25/yet-anothor-better-gif-method/)
* [FFmpeg实用命令：音频、视频格式转换和其它操作 – WTF Daily Blog](http://blog.topspeedsnail.com/archives/1699)
* [使用 ffmpeg 实现 MP4 与 GIF 的互转 · Issue #95 · ameizi/DevArticles · GitHub](https://github.com/ameizi/DevArticles/issues/95)
* [How do I convert a video to GIF using ffmpeg, with reasonable quality? - Super User](https://superuser.com/questions/556029/how-do-i-convert-a-video-to-gif-using-ffmpeg-with-reasonable-quality)