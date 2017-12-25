---
layout: post
title:  "React CSS Modules 用法教程 留言 (笔记)"
date:   2017-10-06 04:05:10 +0800
categories:  
tags: 
---

tutorial from [CSS Modules 用法教程 - 阮一峰](http://www.ruanyifeng.com/blog/2016/06/css_modules.html)

## 留言（45条）
                

请问css变量可以直接用这个吗？
[https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)

2016年6月10日 12:17
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357413)
 | [引用](#comment-text)

[indooorsman](https://csser.me)

 说：
                

shadow dom可以实现样式隔离

2016年6月10日 14:02
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357418)
 | [引用](#comment-text)

[AnnatarHe](https://AnnatarHe.github.io)

 说：
                

谢谢分享，又学习了 ^_^

2016年6月10日 20:59
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357421)
 | [引用](#comment-text)

[黑仔](http://0715huazhuang.com)

 说：
                

勤奋啊！说转技术就转技术了，厉害！

2016年6月11日 17:26
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357475)
 | [引用](#comment-text)

[ubuntugx](http://ubuntugx.com)

 说：
                

刚刚学习完 CSS Module，想写个博文记录一下，不知从哪里开始写，把想法表达清楚真是一种能力，必须要理解透彻才行。佩服阮老师。

2016年6月11日 21:30
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357478)
 | [引用](#comment-text)

leeleo

 说：
                

阮老师高产似母猪.

说实话,看阮老师的blog,工资涨得好快.

2016年6月12日 17:18
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357519)
 | [引用](#comment-text)

[晚晴幽草轩](http://www.jeffjade.com)

 说：
                

学习了，感谢阮先生。明天去实验一下，说不定正好可以以此解决一个固有问题（同套js[vue+webpack实现]逻辑下，因需求不同衍生出不同themes的多版本activity）。

2016年6月13日 02:08
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357533)
 | [引用](#comment-text)

郁也风

 说：
                

相比 postcss，使用 less 或 sass 结合 module 更好用

2016年6月13日 03:04
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357534)
 | [引用](#comment-text)

[阮凯](http://www.cnblogs.com/clear93/)

 说：
                

阮大师我的学习目标。

2016年6月17日 15:05
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-359340)
 | [引用](#comment-text)

CCY

 说：
                

用这个会对浏览器调试有影响吧

2016年6月27日 09:58
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-359773)
 | [引用](#comment-text)

NicholasNC

 说：
                

阮老师，请问有了CSS Module，是不是不需要Sass了。或者说，有结合使用Sass的必要吗？

2016年6月28日 11:42
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-359855)
 | [引用](#comment-text)

jk

 说：
                

请问css modules 可以用于web端网站吗？

2016年7月 5日 15:45
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360235)
 | [引用](#comment-text)

Beier

 说：
                

看了您的博客，突然发觉自己以前的思维太狭隘了，现在真的有一种站在巨人肩膀上的感觉。

2016年7月 8日 09:59
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360351)
 | [引用](#comment-text)

[Alvin](http://www.xuehtml.com)

 说：
                

在react项目中，我一个标签需要用到多个样式时   转换成 

2016年7月 8日 14:34
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360373)
 | [引用](#comment-text)

[Alvin](http://www.xuehtml.com)

 说：
                

在react项目中，我一个标签需要用到多个样式时 <div className="title1 title2 title3">  转换成 <div className={style.title1} 这种形式，怎么写？

2016年7月 8日 14:36
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360375)
 | [引用](#comment-text)

[Alvin](http://www.xuehtml.com)

 说：
                

>     引用Alvin的发言：
> 
> 
> 在react项目中，我一个标签需要用到多个样式时 <div className="title1 title2 title3">转换成 <div className={style.title1} 这种形式，怎么写？

后来我想到一个办法，这样 ：className={[style.title1,style.title2,style.title3].join(" ")}

2016年7月 8日 15:28
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360383)
 | [引用](#comment-text)

[renpingjun](http://segmentfault.com/u/renpingjun)

 说：
                

哈希之后，代码后期维护会变得很困难，找个类半天

2016年7月12日 10:18
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360540)
 | [引用](#comment-text)

zhaozhiming

 说：
                

>     引用Alvin的发言：
> 
> 
> 后来我想到一个办法，这样 ：className={[style.title1,style.title2,style.title3].join(" ")}

用 classnames 包

2016年7月19日 12:04
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-360864)
 | [引用](#comment-text)

MoonBall

 说：
                

base64 转换 .title 结果不是 ._3zyde4l1yATCOkgn-DBWEL，应该还加入了其他信息。

2016年8月 3日 12:19
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-361643)
 | [引用](#comment-text)

[qshting](http://无)

 说：
                

感觉不是很好用呀，后期调试，名称不统一。

2016年8月17日 15:47
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-362529)
 | [引用](#comment-text)

silence

 说：
                

到目前为止看到的各种技术都只是在工程化方向发展而无本质的进化~~~偷懒而已，还美其名曰“提高效率，节约成本”

2016年8月19日 11:15
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-362630)
 | [引用](#comment-text)

[liu](https://github.com/liu-dongyu)

 说：
                

>     引用zhaozhiming的发言：
> 
> 
> 用 classnames 包

直接用es6的 `${}` 链接就好了

`${style.title1} ${style.title2}`

2016年8月22日 09:41
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-362879)
 | [引用](#comment-text)

[riskers](http://riskers.github.io)

 说：
                

可以在非 React 中使用么

2016年9月12日 15:28
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-364352)
 | [引用](#comment-text)

杨名远

 说：
                

请问怎么在global下面 生成sass的全局变量 和函数呢？？

2016年11月19日 11:43
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-368728)
 | [引用](#comment-text)

jsasg

 说：
                

请问react-css-modules是不是有兼容问题

在android微信里react-css-modules写法页面打不开

2016年12月 1日 15:52
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-369575)
 | [引用](#comment-text)

loszer

 说：
                

阮老师，css modules算是一种主流的做法吗

2016年12月18日 21:03
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-370557)
 | [引用](#comment-text)

菜鸟

 说：
                

好好的css给糟蹋成什么样子了 —— 乱七八糟。

2017年2月28日 17:48
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-373624)
 | [引用](#comment-text)

Ve

 说：
                

less和sass应该怎么做到局部作用域？

2017年3月13日 10:13
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-374653)
 | [引用](#comment-text)

teynui

 说：
                

class是不是只能用驼峰的写法？能用className={style.pass-bar}的写法吗?貌似会报错,求解决办法

2017年5月11日 11:27
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-377052)
 | [引用](#comment-text)

小2b哔哔哔哔哔

 说：
                

想请问一下 css modules 有没有 sublime 的语法插件？针对 :global{} 多层嵌套的颜色高亮有点反常

2017年6月12日 11:38
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-377889)
 | [引用](#comment-text)

Jack

 说：
                

>     引用菜鸟的发言：
> 
> 
> 好好的css给糟蹋成什么样子了 —— 乱七八糟。

这并不是糟蹋，你只是没去用，这些东西都是非常好的处理细节，当项目非常大，这些东西的威力就会体现出来

2017年6月13日 16:52
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-377925)
 | [引用](#comment-text)

webster

 说：
                

很给力 一遍就看懂了 3Q !

2017年8月 3日 16:28
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-379216)
 | [引用](#comment-text)

致家驹

 说：
                

扶我起来^_^

2017年8月 5日 20:52
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-379283)
 | [引用](#comment-text)

[伍云江](http://wuyunjiang.cn)

 说：
                

原来dva里面使用的就是这种方式，以前在css都没用到这些方法

2017年8月11日 09:07
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-379439)
 | [引用](#comment-text)

文栋梁

 说：
                

全局css样式表也会被处理，这个怎么解决

2017年8月21日 14:41
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-379687)
 | [引用](#comment-text)

josh

 说：
                

@keyframes 怎么用:local 

2017年9月20日 13:47
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-380650)
 | [引用](#comment-text)

[hru](http://jackhan.net)

 说：
                

请问引入cssmodule这个时候再引入第三方UI库就会导致第三方UI库也被改成哈希类名，但是第三方库的js却没有变，导致样式显示不出

2017年10月21日 19:22
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-381534)
 | [引用](#comment-text)

[Kerita](http://kerita.github.io)

 说：
                

>     引用Alvin的发言：
> 
> 
> 后来我想到一个办法，这样 ：className={[style.title1,style.title2,style.title3].join(" ")}

用 classnames 这个包也可以

2017年10月25日 16:01
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-381668)
 | [引用](#comment-text)

吃小锅米线

 说：
                

按照阮教授这么解释css modules的用法，我是不是可以在项目里定义一个全局的.css文件(例如app.css)，里面全部都是:global。然后在每个js里都引用一下(目的是确保统一的公共样式，以便以后要更换公共样式的时候，我只需要修改app.css就可以了)。然后在引一个属于自己的.css文件(用来编写:local的样式)。

2017年11月 1日 16:37
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-381881)
 | [引用](#comment-text)

[05](https://github.com/msforest)

 说：
                

阮老师你好，请问这个css modules能直接定义html标签吗？就是不使用class定义样式

2017年11月 8日 15:19
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-382145)
 | [引用](#comment-text)

[05](https://github.com/msforest)

 说：
                

阮老师您好，我有一个问题：在开发的过程中，使用到css-modules来加载css，但是现在我们的配置是对自己写的样式采用css-modules，而node_modules里采用全局引入，现在我的一个全局引入的样式覆盖了其他人引入的全局样式；我想问，有没有一种方法--我把node_modules里的css引入到我自定义的css文件中，变成局部样式，且引入的样式不会使用css-modules来进行hash转义？请阮老师指教，谢谢[/抱拳]

2017年11月 8日 15:31
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-382147)
 | [引用](#comment-text)

prc333

 说：
                

less怎么配置css modules？

2017年11月28日 16:26
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-382806)
 | [引用](#comment-text)

[chjiyun](http://me.chjiyun.com)

 说：
                

请问各位大哥大姐CSSModule转换了keyframes动画名怎么破，：global 也没用啊。


>     引用chjiyun的发言：
> 
> 
> 请问各位大哥大姐CSSModule转换了keyframes动画名怎么破，：global 也没用啊。

同求解



