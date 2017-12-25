---
layout: post
title:  "爬虫google"
date:   2016-08-04 11:17:32 +0800
categories: jekyll update
--- 

## 爬虫google ##

### urllib 和 urllib2 的区别 ###

urllib只可以接收URL，
urllib2可以接受一个Request类的实例来设置URL请求的headers，  
可以伪装user agent 等(下面会用到)。

python beautifulsoup多线程分析抓取网页  
python SGMLParser  
python google api   



这样写会报错：

    def search(queryStr):
        queryStr = urllib2.quote(queryStr)
        url = 'https://www.google.com.hk/search?hl=en&q=%s' % queryStr
        request = urllib2.Request(url)
        print url
        response = urllib2.urlopen(request)
        html = response.read()
        results = self.extractSearchResults(html)
        print results

    python_google_api.search("ABC")

代码执行到

	response = urllib2.urlopen(request)

报错

	File "C:\Python27\Lib\site-packages\wj7\x\test\python_google_api.py", line 53, in <module>
	  main()
	File "C:\Python27\Lib\site-packages\wj7\x\test\python_google_api.py", line 47, in main
	  python_google_api.search("ABC")
	File "C:\Python27\Lib\site-packages\wj7\x\test\python_google_api.py", line 31, in search
	  response = urllib2.urlopen(request)
	File "C:\Python27\Lib\urllib2.py", line 154, in urlopen
	  return opener.open(url, data, timeout)
	File "C:\Python27\Lib\urllib2.py", line 437, in open
	  response = meth(req, response)
	File "C:\Python27\Lib\urllib2.py", line 550, in http_response
	  'http', request, response, code, msg, hdrs)
	File "C:\Python27\Lib\urllib2.py", line 475, in error
	  return self._call_chain(*args)
	File "C:\Python27\Lib\urllib2.py", line 409, in _call_chain
	  result = func(*args)
	File "C:\Python27\Lib\urllib2.py", line 558, in http_error_default
	  raise HTTPError(req.get_full_url(), code, msg, hdrs, fp)
	
	urllib2.HTTPError: HTTP Error 403: Forbidden

通过浏览器是可以访问的：

	https://www.google.com.hk/search?hl=en&q=ABC

但是这个文件在解析html的时候，不对了。
	
	extractSearchResults


帮助保存网络中立性！免费的开放式互联网再次受到威胁 - 我们需要您的帮助。
学到更多


参考


* [对于python抓取google搜索结果的一些了解 - 简书](http://www.jianshu.com/p/a4d13ba26107) 
* [利用爬虫技术能做到哪些很酷很有趣很有用的事情？ - 知乎](https://www.zhihu.com/question/27621722)
* [关于python抓取google搜索结果的若干问题 - AfterSummer - 博客园](http://www.cnblogs.com/meibenjin/archive/2013/05/01/3053262.html)
* [python 爬虫，爬取google搜索结果，爬一段时间就被噤掉了，怎么破_百度知道](https://zhidao.baidu.com/question/373688011501697404.html)
* [python抓取google搜索结果 - 软件开发 - Web开发](http://www.fiw3.com/m/python-zhua-qu-google-sou-suo-jie-guo.html)
* [python抓取google搜索结果_技术栈](http://www.jishux.com/plus/view-464348-1.html)
* [使用Python爬取Google搜索结果 - Jokers's Notes](http://thathub.com/2017/09/06/googleScraping/)
* [python之由公司名推算出公司官网(余弦相似度) - 简书](http://www.jianshu.com/p/d1cf6c6df6bb)