---
layout: post
title:  "laravel 安装windows"
date:   2018-02-08 17:59:10 +0800
categories:  
tags: 
---


### 安装windows laravel

在windows使用exe安装包安装

##
Composer Proxy Setting
Composer Proxy Setting 设置

问题：

在ps运行报错：

`
laravel new vue-app
'laravel' 不是内部或外部命令，也不是可运行的程序
`

命令行
`
composer create-project laravel/laravel your-project-name --prefer-dist
`





https://blog.csdn.net/shenjf2000/article/details/47809727

### “修改 composer 的配置文件
参考：
http://pkg.phpcomposer.com/ 


composer create-project laravel/laravel your-project-nam
 --prefer-dist

### 创建learnlaravel5

使用命令行安装learnlaravel5

`
composer create-project laravel/laravel learnlaravel5 5.0.22
` 

然后，稍等片刻，当前目录下就会出现一个叫learnlaravel5 的文件夹。
`
  [Symfony\Component\Debug\Exception\FatalErrorException]
  Cannot use 'PhpParser\Node\Scalar\String' as class name as it is reserved

Script php artisan optimize handling the post-install-cmd event returned with error code 255
`



### 如果从git安装包安装，那么使用安装 composer install
`
composer install
`

### 浏览
composer laravel启动
ps
`
http://127.0.0.1/项目文件夹名/public
`
http://localhost:8000

php artisan serve
vue subl.

laravel new-app

npm install
composer install

laravel open
npm run watch laravel composer



#### 参考 ####

* [Web开发之PHP框架（一）-Laravel环境搭建 - CSDN博客](https://blog.csdn.net/shenjf2000/article/details/47809727) 
* [Windows环境下Composer的安装教程 - 简书](https://www.jianshu.com/p/5b697ccf80fc) 
* [LikeLaravel/install.md at master · maliang/LikeLaravel](https://github.com/maliang/LikeLaravel/blob/master/base/install.md)
* [Laravel 5 系列入门教程（一）【最适合中国人的 Laravel 教程】 - 岁寒](https://lvwenhan.com/laravel/432.html)
* [laravel 安装、启动、工作流程](https://www.jianshu.com/p/27b83f6c86d4)