---
layout: post
title:  "mp4转gif ffmpeg"
date:   2017-12-07 22:52:41 +0800
categories:  public
tags: gif ffmpeg
---

## 小结 ##


1. 用Boilsoft裁剪视频。不折腾。比较快。 
2. 录屏时间长一点，这样用Boilsoft裁剪视频，错位就不那么明显。

其他：

1. 小软件有同样的问题：裁剪的时间点不准确，格式工厂，Boilsoft Video Splitter，Xilisoft Video Cutter；
2. 专业软件操作麻烦。Premier没有搞懂怎么设置原始尺寸不变。
2. iMovie不能设置尺寸，默认的电视机横屏。
3. 机器安装会声会影和Premier报错；没有vc_red.msi，  
Microsoft Visual C++ 2008 Redistributable无法修复，无法卸载。
5. 不懂怎么把iphone录屏保存到Mac，iTunes没找到功能。
6. Mac能连线iPhone录屏。没有试过。 


# 步骤 #

## 1 裁剪mp4前后帧
【版本】Boilsoft Video Splitter 6.34.4  
【备要】 
uVideoSplitter.py
调用
VideoSplitterBat.py
调用
VideoSplitter loader.exe

注意1：
处理后文件名有变化：  
CVZK3966.MP4 ->
CVZK3966.m4v  

注意2：
长的视频可以。  
过短的视频不行，必须Adobe Premier


	Automatic encoder selection failed for output stream #0:1. Default encoder for format 3gp (codec amr_nb) is probably disabled. Please choose an encoder manually.
	Error selecting an encoder for stream 0:1

Xilisoft Video Cutter 2 for Mac 2.0.1

在iphone6用手机录屏。
在mac使用iMovie转视频，
会在左右2边填充黑色。

mac转视频 长度和宽度相反

# 2 裁剪区域
【版本】ffmpeg version 3.4 Copyright (c) 2000-2017 the FFmpeg developers
  built with gcc 7.2.0 (GCC)


【】苹果6的录屏尺寸是720x1280。转小：640x1138
【备要】 

	
	ffmpeg -i CVZK3966.m4v -vf "crop=640:1138:0:0" CVZK3966-cut.m4v

报错：

	[Parsed_crop_0 @ 00000000036bff00] Invalid too big or non positive size for widt
	h '640' or height '1138'
	[Parsed_crop_0 @ 00000000036bff00] Failed to configure input pad on Parsed_crop_
	0
	Error reinitializing filters!
	Failed to inject frame into filter network: Invalid argument
	Error while processing the decoded data for stream #0:0

改成：

	ffmpeg -i CVZK3966-32.gif -vf "crop=640:1096:0:42" -y CVZK3966-32-cut.gif
	
	-y, 覆盖输出文件

参考：

>
	ffmpeg -i input.m4v -vf scale=iw/2:-1,crop=ih output.m4v
> scale=width:height iw/ih 表示输入宽度/高度 -1 表示按输入尺寸等比自动计算  
> crop=width:height:x:y 
> x:y 指定裁剪的左上角位置，默认值为 (in_w-out_w)/2 和 (in_h-out_h)/2，即输出视频为原视频的中央区域  

报错2： 

如果是用iMovie来裁剪的，则本来的录屏时候的640x1136变成了

报错：

	[Parsed_crop_0 @ 0000000002c55d40] Invalid too big or non positive size for widt
	h '640' or height '1138'
	[Parsed_crop_0 @ 0000000002c55d40] Failed to configure input pad on Parsed_crop_
	0
	Error reinitializing filters!
	Failed to inject frame into filter network: Invalid argument
	Error while processing the decoded data for stream #0:0


安装会声会影报错：

	Windows Installer
	The feature you are trying to use is on a network resource that is unavailable.
	
	Click OK to try again, or enter an alternate path to a folder containing the installation package 'vc_red.msi' in the box below.
	
	c:\01ecb6d29e7f1caed63c\

安装vc_red.msi报错：

	Microsoft Visual C++ 2008 Redistributable - x86 9.0.30729.4148
	Error 1311.Source file not found: E:\n\sys\pack3\video\vc_red.cab.  Verify that the file exists and that you can access it.

	&Retry Cancel


+vc_red.cab后，安装报错：
	
	Microsoft Visual C++ 2008 Redistributable - x86 9.0.30729.4148

	Error 1334.The file 'ul_catalog.30729.4148.Microsoft_VC90_OpenMP_x86.QFE' cannot be installed because the file cannot be found in cabinet file 'vc_red.cab'. This could indicate a network error, an error reading from the CD-ROM, or a problem with this pac


安装后报错：c:\90d7f034697c37ba38\
	
	Windows Installer
	无法访问您试图使用的功能所在的网络位置。
	单击“确定”重试，或在下面的框中输入包含安装程序包“vc_red.msi”的文件夹的路径。
	使用源(&U):
	c:\90d7f034697c37ba38\


vc_red.msi是什么？
这些文件是vc2008再发行组件包安装时产生的临时文件,但这个软件却因为bug问题而错误的将临时文件放到了f盘更目录(本应该是temp目录并会被自动删除的,并且这个bug是微软已知的bug)
可删除，ME以前删除没发现有什么影响！！
	
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

cd E:\n\wj\171207_blogAuto\video
压缩gif.bat

	cd E:\n\wj\171207_blogAuto\video
	convert CVZK3966-32-320.gif -fuzz 5% -layers Optimize CVZK3966-32-320-compress.gif

报错：

	E:\n\wj\171207_blogAuto\video>convert CVZK3966-32-320.gif -fuzz 5% -layers Optimize CVZK3966-32-320-compress.gif
	无效参数 - -fuzz

convert是windows的分区自带的类型转换程序       
加上 magick：  

	magick convert CVZK3966-32-320.gif -fuzz 5% -layers Optimize CVZK3966-32-320-compress.gif

CVZK3966-32-320.gif            25M
CVZK3966-32-320-compress.gif   26M


### 切换gif图片 ###

[小tips: CSS或JS实现gif动态图片的停止与播放](http://www.zhangxinxu.com/wordpress/2015/12/css3-animation-js-canvas-gif-pause-stop-play/)

### gif图片加水印 ###

	ffmpeg -i test.mp4 -i logo.png -filter_complex overlay test1.mp4


改变位置：

写法1：

	ffmpeg -i CVZK3966-32-cut.gif -i watermark.png -filter_complex overlay=0:90 -y CVZK3966-32-add-mask.gif

写法2：

	::ffmpeg -y -i CVZK3966-32-cut.gif  -vf "movie=watermark.png [wm];[in][wm] overlay=0:90 [out]" -strict experimental CVZK3966-32-add-mask.gif

[FFmpeg总结（十）用ffmpeg进行在视频中加水印图、加gif图](http://blog.csdn.net/hejjunlin/article/details/71104027)

### gif导出序列帧 ###


### ffmpeg 旋转方向 ###

代码1：无效.  

	ffmpeg -i CVZK3966-cut.mp4 -metadata:s:v rotate="90" -codec copy -y  CVZK3966-cut-90.mp4

代码2：注意8种写法，各不相同。

	
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=0" -y  CVZK3966-cut-90-0.mp4  
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=1" -y  CVZK3966-cut-90-0.mp4  
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=2" -y  CVZK3966-cut-90-0.mp4  
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=3" -y  CVZK3966-cut-90-0.mp4  

	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=0,transpose=0" -y  CVZK3966-cut-90-0.mp4  
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=1,transpose=1" -y  CVZK3966-cut-90-0.mp4 
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=2,transpose=2" -y  CVZK3966-cut-90-0.mp4   
	ffmpeg -i CVZK3966-cut.mp4 -vf "transpose=3,transpose=3" -y  CVZK3966-cut-90-0.mp4  

### 作品页检查器 ###
目的： 用来检查过往项目的网页材料准备。是否完成。 
x=未完成，1=已经完成
![一个检查器](https://i.imgur.com/aX3hyY8.png) 
工具：python2.7+powershell3.0  +acp1.0   
FlashDevelop 4.6.4.1 for .net2.0  


使用sharex上传图片。  



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