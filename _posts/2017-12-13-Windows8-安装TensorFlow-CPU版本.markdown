---
layout: post
title:  "Windows8 安装TensorFlow-CPU版本"
date:   2017-12-13 18:40:13 +0800
categories:  
tags: 
---



参考：https://www.tensorflow.org/install/install_windows
 
## 环境 ##
 
TensorFlow是基于VC++2015开发的，  
要下载安装VisualC++ Redistributable for Visual Studio 2015  获取MSVCP140.DLL的支持。 
 
## 安装 ##
  
1. 下载安装Python 3.5.x 64-bit，要注意版本3.5.x。
2. 打开windows的命令行窗口，安装CPU版本输入

		pip3install --upgrade tensorflow

 
### 验证 ###

或者运行python3.5命令行后输入以下代码：

	importtensorflow as tf
	hello = tf.constant('Hello, TensorFlow!')
	sess = tf.Session()
	print(sess.run(hello))

输出hello字符串，则安装成功。

	Hello, TensorFlow!
 
### 错误 ###

其中一个经常遇到的错误就是No module named "pywrap_tensorflow" 或者 “Failed toload the native TensorFlow runtime”，其产生的原因主要是安装环境不满足要求，参考如下链接解答：  

https://stackoverflow.com/questions/43942185/failed-to-load-the-native-tensorflow-runtime-python-3-5-2
https://stackoverflow.com/questions/42011070/on-windows-running-import-tensorflow-generates-no-module-named-pywrap-tenso

#### 参考 ####


* [Windows下安装TensorFlow快速教程 - 豆芽菜 - CSDN博客](http://blog.csdn.net/dou3516/article/details/77836459)
* [window 安装 tensorflow - CSDN博客](http://blog.csdn.net/hai4321/article/details/78438981)
* [Windows10 64位下安装TensorFlow - CSDN博客](http://blog.csdn.net/zhunianguo/article/details/53536425)
* [Windows8.1&&10 安装 Tensorflow 遇到的问题 - bluesliuf的博客 - CSDN博客](http://blog.csdn.net/bluesliuf/article/details/78004578)