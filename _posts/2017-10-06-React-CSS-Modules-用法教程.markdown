---
layout: post
title:  "React CSS Modules 用法教程"
date:   2017-10-06 11:32:17 +0800
categories:  
tags:  
    - react

---

tutorial from [CSS Modules 用法教程 - 阮一峰](http://www.ruanyifeng.com/blog/2016/06/css_modules.html)

[CSS Modules](https://github.com/css-modules/css-modules) 功能单纯，仅局部作用域和模块依赖。


## 零、安装Demo

[6个Demo](https://github.com/ruanyf/css-modules-demos)  
powershell  
```powershell
cd E:\n\learn\react\css
git clone https://github.com/ruanyf/css-modules-demos.git
Rename-Item css-modules-demos ryf
cd ryf
npm install
npm run demo01
cd E:\n\learn\react\css\ryf
```
powershell 重命名文件夹  
http://localhost:8080  
![](https://i.imgur.com/kZbfJ6o.png)

Create winform interface is a easy task and  happy experience in coding with powershell, which is  harder created in C# with visual studio in developing a same function. The code will be very clear without complex communication object. Also we will catch the error message in terminal easily instead of avoiding the complex debug system in vs.

The communication betweeen powershell and python is very simple. Just only one statements likes below, could be input the data from python file:
```powershell

```
and make as script to reflect python file. 
In this way that the ui-interface could be created handy and easily  

## 一、局部作用域
`class`用唯一随机名。

demo01/components/App.js
```js
import React from 'react';
import style from './App.css';

export default () => {
  return (
    <h1 className={style.title}>
      Hello World
    </h1>
  );
}; 
```

这里的style，指向`App.css`,style.title,指向App.css中的class定义`.title {`。 

demo01/components/App.css
```css
.title {
  color: red;
}

```


构建工具会将类名`style.title`编译成哈希字符串。

>     <h1class="_3zyde4l1yATCOkgn-DBWEL">
>       Hello World
>     </h1>

`App.css`也会同时被编译。

```css
>     ._3zyde4l1yATCOkgn-DBWEL {color: red;}
```

类名变成独一无二，只对`App`组件有效。

CSS Modules 提供各种[插件](https://github.com/css-modules/css-modules/blob/master/docs/get-started.md)，支持不同的构建工具。本文使用的是 Webpack 的[`css-loader`](https://github.com/webpack/css-loader#css-modules)插件，因为它对 CSS Modules 的支持最好，而且很容易使用。

下面是的`webpack.config.js`。
webpack.config.js
```js
>     
>     module.exports ={
>       entry: __dirname +'/index.js',
>       output:{
>         publicPath:'/',
>         filename:'./bundle.js'},
>       module:{
>         loaders:[{
>             test:/\.jsx?$/,
>             exclude:/node_modules/,
>             loader:'babel',
>             query:{
>               presets:['es2015','stage-0','react']}},{
>             test:/\.css$/,
>             loader:"style-loader!css-loader?modules"},]}};
```

上面代码中，关键的一行是`style-loader!css-loader?modules`，它在`css-loader`后面加了一个查询参数`modules`，表示打开 CSS Modules 功能。

现在，运行这个Demo。

>     
>     $ npm run demo01
>     

打开 http://localhost:8080 ，可以看到[结果](http://ruanyf.github.io/css-modules-demos/demo01/)，`h1`标题显示为红色。

## 二、全局作用域

CSS Modules 允许使用`:global(.className)`的语法，声明一个全局规则。凡是这样声明的`class`，都不会被编译成哈希字符串。

[`App.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo02/components/App.css)加入一个全局`class`。

>     .title {color: red;}:global(.title) {color: green;}

[`App.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo02/components/App.css)使用普通的`class`的写法，就会引用全局`class`。

>     
>     import React from 'react';
>     import styles from './App.css';
>     
>     export default ()=>{return(<h1 className="title">
>           Hello World
>         </h1>);};

运行这个示例。

>     
>     $ npm run demo02
>     

打开 http://localhost:8080，应该会[看到](http://ruanyf.github.io/css-modules-demos/demo02/)`h1`标题显示为绿色。

CSS Modules 还提供一种显式的局部作用域语法`:local(.className)`，等同于`.className`，所以上面的`App.css`也可以写成下面这样。

>     :local(.title) {color: red;}:global(.title) {color: green;}

## 三、定制哈希类名

`css-loader`默认的哈希算法是`[hash:base64]`，这会将`.title`编译成`._3zyde4l1yATCOkgn-DBWEL`这样的字符串。

[`webpack.config.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo03/webpack.config.js)里面可以定制哈希字符串的格式。

>     
>     module:{
>       loaders:[ // ...
>     {
>           test:/\.css$/,
>           loader:"style-loader!css-loader?modules&localIdentName=[path][name]---[local]---[hash:base64:5]"},]}

运行这个示例。

>     
>     $ npm run demo03
>     

你会[发现](http://ruanyf.github.io/css-modules-demos/demo03/)`.title`被编译成了`demo03-components-App---title---GpMto`。

## 四、 Class 的组合

在 CSS Modules 中，一个选择器可以继承另一个选择器的规则，这称为"组合"（["composition"](https://github.com/css-modules/css-modules#composition)）。

在[`App.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo04/components/App.css)中，让`.title`继承`.className` 。

>     .className {background-color: blue;}.title {composes: className;color: red;}

[`App.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo04/components/App.js)不用修改。

>     
>     import React from 'react';
>     import style from './App.css';
>     
>     export default ()=>{return(<h1 className={style.title}>
>           Hello World
>         </h1>);};

运行这个示例。

>     
>     $ npm run demo04
>     

打开`http://localhost:8080`，会[看到](http://ruanyf.github.io/css-modules-demos/demo04/)红色的`h1`在蓝色的背景上。

`App.css`编译成下面的代码。

>     ._2DHwuiHWMnKTOYG45T0x34 {color: red;}._10B-buq6_BEOTOl9urIjf8 {background-color: blue;}

相应地， `h1`的`class`也会编译成`<h1 class="_2DHwuiHWMnKTOYG45T0x34 _10B-buq6_BEOTOl9urIjf8">`。

## 五、输入其他模块

选择器也可以继承其他CSS文件里面的规则。

[`another.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo05/components/another.css)

>     .className {background-color: blue;}

[`App.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo05/components/App.css)可以继承`another.css`里面的规则。

>     .title {composes: className from './another.css';color: red;}

运行这个示例。

>     
>     $ npm run demo05
>     

打开`http://localhost:8080`，会[看到](http://ruanyf.github.io/css-modules-demos/demo05/)蓝色的背景上有一个红色的`h1`。

## 六、输入变量

CSS Modules 支持使用变量，不过需要安装 PostCSS 和 [postcss-modules-values](https://github.com/css-modules/postcss-modules-values)。

>     
>     $ npm install --save postcss-loader postcss-modules-values
>     

把`postcss-loader`加入[`webpack.config.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo06/webpack.config.js)。

>     var values =require('postcss-modules-values');
>     
>     module.exports ={
>       entry: __dirname +'/index.js',
>       output:{
>         publicPath:'/',
>         filename:'./bundle.js'},
>       module:{
>         loaders:[{
>             test:/\.jsx?$/,
>             exclude:/node_modules/,
>             loader:'babel',
>             query:{
>               presets:['es2015','stage-0','react']}},{
>             test:/\.css$/,
>             loader:"style-loader!css-loader?modules!postcss-loader"},]},
>       postcss:[
>         values
>       ]};

接着，在[`colors.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo06/components/colors.css)里面定义变量。

>     @value blue: #0c77f8;@value red: #ff0000;@value green: #aaf200;

[`App.css`](https://github.com/ruanyf/css-modules-demos/tree/master/demo06/components)可以引用这些变量。

>     @value colors: "./colors.css";@value blue, red, green from colors;.title {color: red;background-color: blue;}

运行这个示例。

>     
>     $ npm run demo06
>     

打开`http://localhost:8080`，会[看到](http://ruanyf.github.io/css-modules-demos/demo06/)蓝色的背景上有一个红色的`h1`。

（完）

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

#### 参考 ####

