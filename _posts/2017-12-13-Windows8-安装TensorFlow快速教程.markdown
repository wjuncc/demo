---
layout: post
title:  "Windows8 安装TensorFlow快速教程"
date:   2017-12-13 18:40:13 +0800
categories:  
tags: 
---

# Windows8 安装TensorFlow快速教程 #
Windows下安装TensorFlow快速教程



参考：https://www.tensorflow.org/install/install_windows
 
一、安装环境
TensorFlow即可以支持CPU，也可以支持CPU+GPU。前者的环境需求简单，后者需要额外的支持。TensorFlow是基于VC++2015开发的，所以需要下载安装VisualC++ Redistributable for Visual Studio 2015 来获取MSVCP140.DLL的支持。如果要安装GPU版本（有N卡，即NVIDIA显卡），需要以下额外环境：
0）有支持CUDA计算能力3.0或更高版本的NVIDIAGPU卡。
1）下载安装CUDA Toolkit 8.0，并确保其路径添加到PATH环境变量里；
2）下载安装cuDNN v6或v6.1，并确保其路径添加到PATH环境变量里；
3）CUDA8.0相关的NVIDIA驱动。
 
二、安装过程
         具备了上述安装条件（CPU或GPU）之后，TensorFlow可以通过两种方式进行安装。一是”native” pip，二是Anaconda。推荐前者，比较简单。
一）使用”native” pip安装
1）下载安装Python 3.5.x 64-bit，要注意版本3.5.x。
2）打开windows的命令行窗口，安装CPU版本输入
pip3install --upgrade tensorflow
安装GPU版本输入
pip3install --upgrade tensorflow-gpu
         二）使用Anaconda安装
1）下载安装Anaconda；
2）打开命令行窗口，创建conda环境
condacreate -n tensorflow python=3.5
3）激活conda环境
activatetensorflow
4）安装CPU版本输入
pipinstall --ignore-installed --upgrade tensorflow
安装GPU版本输入
pipinstall --ignore-installed --upgrade tensorflow-gpu
 
三、验证安装
         验证TensorFlow安装是否成功，可以在命令行窗口输入python进入python环境，或者运行python3.5命令行后输入以下代码：
>>> importtensorflow as tf
>>> hello = tf.constant('Hello, TensorFlow!')
>>> sess = tf.Session()
>>> print(sess.run(hello))
如果能正常输出hello字符串，则安装成功。
Hello, TensorFlow!
 
四、安装错误
         常见的安装错误参考链接，其中一个经常遇到的错误就是No module named "pywrap_tensorflow" 或者 “Failed toload the native TensorFlow runtime”，其产生的原因主要是安装环境不满足要求，参考如下链接解答：
https://stackoverflow.com/questions/43942185/failed-to-load-the-native-tensorflow-runtime-python-3-5-2
https://stackoverflow.com/questions/42011070/on-windows-running-import-tensorflow-generates-no-module-named-pywrap-tenso

#### 参考 ####

* [Windows下安装TensorFlow快速教程 - 豆芽菜 - CSDN博客](http://blog.csdn.net/dou3516/article/details/77836459)
* [window 安装 tensorflow - CSDN博客](http://blog.csdn.net/hai4321/article/details/78438981)
* [Windows10 64位下安装TensorFlow - CSDN博客](http://blog.csdn.net/zhunianguo/article/details/53536425)
* [Windows8.1&&10 安装 Tensorflow 遇到的问题 - bluesliuf的博客 - CSDN博客](http://blog.csdn.net/bluesliuf/article/details/78004578)