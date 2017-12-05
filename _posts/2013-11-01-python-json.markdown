---
layout: post
title:  "python读取json文件解析json文件"
date:   2013-11-21 01:17:32 +0800
categories: python
cats: python json
---

## python读取json文件解析json文件 ##

### 范例 ###

	import json

	#读取json文件
    jsonStr = uNow.read_fast_return(path)
    jsonStr = jsonStr.decode('utf8','ignore')
    obj = json.loads(jsonStr) 


	#获取python文件对应的配置文件json 
    path = uStringPath.replace_suffix(__file__, ".json")

### 注意 ###
注意3点：

* Python2.6开始有json模块
* 键值对的键名，要加上双引号
* 反斜杠要写2次，写1次报错，
	* 键值对中的值，如果是正则，用反斜杠写2次
	* 键值对中的值，如果是路径，用斜杠写1次，用反斜杠写2次



### 报错 ###

报错： 

	ValueError: Expecting property name enclosed in double quotes

解决：键值对的键名，要加上双引号

报错： 

	ValueError: Invalid \escape: line 7 column 16 (char 113)

解决：斜杠要写2次，写一次报错


参考： 

* [python解析json文件](http://blog.csdn.net/dyx404514/article/details/50186413)
* [Python解析json之ValueError: Expecting property name enclosed in double quotes: line 1 column 2 (char 1)](http://blog.csdn.net/blueheart20/article/details/69704518)
* [[python] python读取json文件解析json文件](https://wjuncc.github.io/demo/jekyll/update/2013/11/21/python-json.html)

