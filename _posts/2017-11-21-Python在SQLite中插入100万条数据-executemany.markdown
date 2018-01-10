---
layout: post
title:  "Python在SQLite中插入100万条数据 executemany"
date:   2017-11-21 17:47:36 +0800
categories:  
tags: 
---


Order: Insert date over 200000 into database.
Recoding each word items as list data in `for` statements and then insert into db with `executemany` method of sqlite3.

Note: Using python3 bit 64 version to accomplish this. Windows7 and python27 bit32 can't do this, for the less of memory. 


当python脚本需要python2运行时，只需在脚本前加上，

```
#! python2
```
当python脚本需要python3运行时，只需在脚本前加上，

```
#! python3
```



同时，这也完美解决了在pip在python2和python3共存的环境下报错，提示Fatal error in launcher: Unable to create process using '"'的问题。

当需要python2的pip时，只需

```
py -2 -m pip install xxx
```

当需要python3的pip时，只需

```
py -3 -m pip install xxx
```

python2和python3的pip package就这样可以完美分开了。


# Python在SQLite中插入100万条数据 executemany #


#### 参考 ####

* [让Python更加充分的使用Sqlite3_慕课手记](https://www.imooc.com/article/20948)
* [月考+通过Python使用Sqlite3的7个技巧 - Python程序员 - 十条](http://www.10tiao.com/html/262/201710/2651376136/1.html)
* [6.8 与关系型数据库的交互 — python3-cookbook 3.0.0 文档](http://python3-cookbook.readthedocs.io/zh_CN/latest/c06/p08_interact_with_relational_database.html)
* [Sqlite3 批量插入 - CSDN博客](http://blog.csdn.net/majiakun1/article/details/50634841)
* [Python 数据库进阶篇，学习一篇就够了，看完不会你找我--相关文章](http://www.360doc.com/relevant/687369706_more.shtml)
* [用Python进行SQLite数据库操作 - 牛皮糖NewPtone - 博客园](https://www.cnblogs.com/yuxc/archive/2011/08/18/2143606.html)
* [Python信息采集器使用轻量级关系型数据库SQLite](https://zhuanlan.zhihu.com/p/21465713)
* [Python 操作 mysql-插入多条数据 - 互联网 - IT610.com](http://www.it610.com/article/82928.htm)
* [Python向Sqlite批量插入数据，测试硬盘性能 - 简书](https://www.jianshu.com/p/6f78b58535fb)
* [python之数据库操作(sqlite)_守株待兔_新浪博客](http://blog.sina.com.cn/s/blog_71f389090100ujvk.html)