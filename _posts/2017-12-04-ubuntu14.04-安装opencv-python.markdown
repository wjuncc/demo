---
layout: post
title:  "ubuntu14.04 安装opencv python"
date:   2017-12-04 01:17:32 +0800
categories: jekyll update
--- 
## 注意 ##
tensorflow需要安装opencv，  
因为tensorflow的例子里有import cv2

注意2点：

1. python-opencv 不用装opencv
2. python-opencv 安装用 apt-get 不是pip


		sudo apt-get install python-opencv

-----------------------------------------
### 下面不重要了 ###

1. opencv和python-opencv是2个东西，安装顺序有讲究。   
如果先装python-opencv，那么再装opencv，就要删掉python-opencv。不然据说会冲突。


-----------------------------------------

参考

* [★★★★★【LinCV】Ubuntu 15.04下安装python2.7+openCV3.0--2017年02月27日](http://lib.csdn.net/article/opencv/26945)
* [Ubuntu 14.04 安装 OpenCV-3.2.0](http://blog.csdn.net/youngpan1101/article/details/58027049)
* [手把手教你，在Ubuntu上安装OpenCV 3.0 和 Python 2.7+](http://nooverfit.com/wp/%E6%89%8B%E6%8A%8A%E6%89%8B%E6%95%99%E4%BD%A0%EF%BC%8C%E5%9C%A8ubuntu%E4%B8%8A%E5%AE%89%E8%A3%85opencv-3-0-%E5%92%8C-python-2-7/)
* [在树莓派2或树莓派B+上安装Python和OpenCV的教程](http://www.jb51.net/article/63103.htm)
* [Ubuntu16.04下安装OpenCV3.2.0](https://www.cnblogs.com/arkenstone/p/6490017.html)
* [Ubuntu16.04下安装Tensorflow+OPENCV3.1](http://www.jianshu.com/p/69c3de470cc6)
