---
layout: post
title:  "React CSS Modules 用法教程 留言 (笔记)"
date:   2017-10-03 11:05:10 +0800
categories: 
tags:  
    - react

---

tutorial from [CSS Modules 用法教程 - 阮一峰](http://www.ruanyifeng.com/blog/2016/06/css_modules.html)

## 留言（45条）
                

请问css变量可以直接用这个吗？
[https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)

shadow dom可以实现样式隔离

学习了，感谢阮先生。明天去实验一下，说不定正好可以以此解决一个固有问题（同套js[vue+webpack实现]逻辑下，因需求不同衍生出不同themes的多版本activity）。

相比 postcss，使用 less 或 sass 结合 module 更好用
  
用这个会对浏览器调试有影响吧



阮老师，请问有了CSS Module，是不是不需要Sass了。或者说，有结合使用Sass的必要吗？


请问css modules 可以用于web端网站吗？
       

-------------------------------------------
在react项目中，我一个标签需要用到多个样式时 <div className="title1 title2 title3">  转换成 <div className={style.title1} 这种形式，怎么写？


后来我想到一个办法，这样 ：className={[style.title1,style.title2,style.title3].join(" ")}

用 classnames 包 
用 classnames 这个包也可以

直接用es6的 `${}` 链接就好了

`${style.title1} ${style.title2}`

-------------------------------------------

哈希之后，代码后期维护会变得很困难，找个类半天

  
base64 转换 .title 结果不是 ._3zyde4l1yATCOkgn-DBWEL，应该还加入了其他信息。
   

感觉不是很好用呀，后期调试，名称不统一。
  
到目前为止看到的各种技术都只是在工程化方向发展而无本质的进化~~~偷懒而已，还美其名曰“提高效率，节约成本”
    

可以在非 React 中使用么

-------------------------------------------   
                

请问怎么在global下面 生成sass的全局变量 和函数呢？？


请问react-css-modules是不是有兼容问题

在android微信里react-css-modules写法页面打不开

                

阮老师，css modules算是一种主流的做法吗


好好的css给糟蹋成什么样子了 —— 乱七八糟。


less和sass应该怎么做到局部作用域？


class是不是只能用驼峰的写法？能用className={style.pass-bar}的写法吗?貌似会报错,求解决办法

                

想请问一下 css modules 有没有 sublime 的语法插件？针对 :global{} 多层嵌套的颜色高亮有点反常

>     引用菜鸟的发言：
> 
> 
> 好好的css给糟蹋成什么样子了 —— 乱七八糟。

这并不是糟蹋，你只是没去用，这些东西都是非常好的处理细节，当项目非常大，这些东西的威力就会体现出来
           

原来dva里面使用的就是这种方式，以前在css都没用到这些方法
       

全局css样式表也会被处理，这个怎么解决 

@keyframes 怎么用:local   
                

请问引入cssmodule这个时候再引入第三方UI库就会导致第三方UI库也被改成哈希类名，但是第三方库的js却没有变，导致样式显示不出
      

按照阮教授这么解释css modules的用法，我是不是可以在项目里定义一个全局的.css文件(例如app.css)，里面全部都是:global。然后在每个js里都引用一下(目的是确保统一的公共样式，以便以后要更换公共样式的时候，我只需要修改app.css就可以了)。然后在引一个属于自己的.css文件(用来编写:local的样式)。


阮老师你好，请问这个css modules能直接定义html标签吗？就是不使用class定义样式
 

阮老师您好，我有一个问题：在开发的过程中，使用到css-modules来加载css，但是现在我们的配置是对自己写的样式采用css-modules，而node_modules里采用全局引入，现在我的一个全局引入的样式覆盖了其他人引入的全局样式；我想问，有没有一种方法--我把node_modules里的css引入到我自定义的css文件中，变成局部样式，且引入的样式不会使用css-modules来进行hash转义？请阮老师指教，谢谢[/抱拳] 

less怎么配置css modules？

请问各位大哥大姐CSSModule转换了keyframes动画名怎么破，：global 也没用啊。
同求解



