---
layout: post
title:  "React CSS Modules 用法教程"
date:   2017-10-06 11:32:17 +0800
categories:  
tags:  
    - react

---

# CSS Modules 用法教程 #
CSS Modules 用法教程 - 阮一峰的网络日志a.bshareDiv,#bsPanel,#bsMorePanel,#bshareF{border:none;background:none;padding:0;margin:0;font:12px Helvetica,Calibri,Tahoma,Arial,宋体,sans-serif;line-height:14px;}#bsPanel div,#bsMorePanel div,#bshareF div{display:block;}.bsRlogo .bsPopupAwd,.bsRlogoSel .bsPopupAwd,.bsLogo .bsPopupAwd,.bsLogoSel .bsPopupAwd{line-height:16px !important;}a.bshareDiv div,#bsFloatTab div{*display:inline;zoom:1;display:inline-block;}a.bshareDiv img,a.bshareDiv div,a.bshareDiv span,a.bshareDiv a,#bshareF table,#bshareF tr,#bshareF td{text-decoration:none;background:none;margin:0;padding:0;border:none;line-height:1.2}a.bshareDiv span{display:inline;float:none;}div.buzzButton{cursor:pointer;font-weight:bold;}.buzzButton .shareCount a{color:#333}.bsStyle1 .shareCount a{color:#fff}span.bshareText{white-space:nowrap;}span.bshareText:hover{text-decoration:underline;}a.bshareDiv .bsPromo,div.bshare-custom .bsPromo{display:none;position:absolute;z-index:100;}a.bshareDiv .bsPromo.bsPromo1,div.bshare-custom .bsPromo.bsPromo1{width:51px;height:18px;top:-18px;left:0;line-height:16px;font-size:12px !important;font-weight:normal !important;color:#fff;text-align:center;background:url(//static.bshare.cn/frame/images/bshare_box_sprite2.gif) no-repeat 0 -606px;}div.bshare-custom .bsPromo.bsPromo2{background:url(//static.bshare.cn/frame/images/bshare_promo_sprite.gif) no-repeat;cursor:pointer;}.bsBox{display:none;z-index:100000001;font-size:12px;background:url(//static.bshare.cn/frame/images//background-opaque-dark.gif) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}.bsClose{_overflow:hidden;cursor:pointer;position:absolute;z-index:10000000;color:#666;font-weight:bold;font-family:Helvetica,Arial;font-size:14px;line-height:20px;}.bsTop{color:#666;background:#f2f2f2;height:24px;line-height:24px;border-bottom:1px solid #e8e8e8;}.bsTop span{float:left;}.bsFrameDiv,#bsMorePanel{border:none;background:#fff;}.bsReturn{float:right;*margin-right:20px;margin-right:36px;text-align:right;cursor:pointer;line-height:24px;color:#666;opacity:0.5;}#bsReturn:hover{text-decoration:underline;opacity:1;}div.bsClear{clear:both;height:0;line-height:0;overflow:hidden;font-size:0;}.bsSearchDiv{padding:5px 15px;background-color:#fafafa;}.bFind-wrapper-top{background:#fff;border-color:#ccc #aaa #aaa #ccc;border-style:solid;border-width:1px;height:16px;padding:4px;margin:0;}.bFind-wrapper-top input{padding:0 !important;border:none !important;box-shadow:none !important;line-height:16px !important;}.bFind-placeholder{background:url("//static.bshare.cn/css/images/search-icon.gif") no-repeat;display:block;float:left;height:16px;width:16px;}.bFind{background:none;border:none;float:left;font-size:11px !important;height:16px !important;margin-left:3px;outline:none;padding:0;width:400px;}.bsPlatDiv{height:322px;background:#fff;overflow:auto;padding:0 15px;}#bsLogoList{display:block;list-style:none;overflow:hidden;margin:0;padding:0;}#bsLogoList li{float:left;display:inline-block;width:71px;text-align:center;font-size:12px;height:80px;margin:0 !important;}#bsLogoList .bsPlatIcon{cursor:pointer;display:block !important;text-align:center;}#bsLogoList .bsPlatImg{width:32px;height:32px;border:none !important;display:inline-block;}#bsLogoList .bsPlatImg:hover{-moz-border-radius:7px;-webkit-border-radius:7px;border-radius:7px;box-shadow:0 0 15px #a7a8ac;}#bsLogoList .bsPlatName{white-space:nowrap;text-overflow:ellipsis;overflow:hidden;text-align:center;color:#333 !important;margin-top:2px;line-height:140%;*width:70px;}#bsLogoList .bsPromoM{text-align:center;}.bsFooterDiv{height:24px;line-height:24px;padding:0 15px;border-top:1px solid #e8e8e8;background:#f2f2f2;text-align:right;}a.bsLogoLink{color:#666;}.bsLogoLink:hover{text-decoration:underline;}.bsPromoM{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;}.bsNew,.bsHot,.bsRec,.bsAwd{background-position:0 -552px;width:19px;margin:5px auto 1px;line-height:16px;height:18px;font-size:12px;color:#fff;overflow:hidden;}.bsNew{background-position:0 -570px;}.bsRec{width:30px;background-position:0 -588px;}.bsAwd{background:url(//static.bshare.cn/frame/images//promot/promote.gif) no-repeat;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}
if (/mobile/i.test(navigator.userAgent) || /android/i.test(navigator.userAgent)) document.body.classList.add('mobile');

window.addEventListener('load', function(event) {
  setTimeout(function () {
    hab('#sup-post-2');
    hab('#gd1-inner');
  }, 1000);
});

阮一峰的网络日志  » [首页](http://www.ruanyifeng.com/blog/) » [档案](http://www.ruanyifeng.com/blog/archives.html)

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAABGdBTUEAAK/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAUzSURBVHjavFdbbFRVFF3nPjoz7dTWTittaW0jUDRAUqaNojyqREnEQKgfUj9MqqAmhqRt/OCD4CuY+Kckoh+aiGKC+gMJbdHoRysJ8dkhhmJLNdDKtJU+6GMK87j3Hs85d2Z6HzNtMYWb3Dn3NWftvfba+5xNYDl+e6Fkj6yqb/oDRbWq14vlPBLRKCITkxf0ROLt+hNjp1PPSRK4kA3vF1dXNRcWlyA2OQU9eos9opAkAiKxD+XkKO6t15aRWO7J/MgmAZU8MEgexgZHMX518Dh72sYMmVKShnxWuWHdHtxKIDIYTgMuDzgfmSOIQkYMpdUF8OY92Hytt4/jvkg47czzU16iQovM3QFwmNck+Yyduu7D6NA0Z6JR4THntFs9V4tWQg6Ui3s6MwKDncsFTnXKLJhDSeUK3AgPtyhccDzmVs999buRt/1Vm4i0od+hX7+MRG87jPGB/w1u8FPj9xEw7McVrnYuOCvtpjTth3J/nTg99c8LRhKhr6D3dTB5R24bXFwbMXBsyZzeoXaycEpJ95TB09AGX/NpqLVNtw8urnVzLvHjFNxiFqRy2OOHuqUVnue+ACkoWzo4O6lGzTmuHq6nPvY2m9rVqjrIK2rMEKxqyG5NPAKt+wjo0LklgfNxJkZMA3KJvqRUk3z5UFY3QH14P0h+WUY79HPvgv7VuSg4ZRGY1YgZgqXmORccF17sy2ehnf9AeO085K2HQFbtXBScj0LcpgF2cN+WV+DZ/LJQu6gD4R7oV7pBJwbSgtMvfiPoVp56DySwxm7EtkMs1WdAB7qzggsDJKQYsHucSkOudrkiCPWR/fA2nYCn8SNIK4NptSMyAu3sAdDRkIsJdfth0LzSrODUoPNZ4KI9SxJI5UHk7D4GdQfz2us31c7CoHMjRkKuDPHseCMrONVhNcDJwMJpKFVvg9L4OaTiNWm1x789KCqkrXhVBiEz0WYCT2nAzQAD1/vaETv1GrRfP4Vx5cfMNcDPwvP0h0DhanPym7OIf/+O67vcJ1/PCJ4KgdzaUP6Wz+dU+5yIL6fV+PsHGAOdwlPpvvUOyeeAVGyCdqkDNB6DPjsBSrnndfOGevOh3RhGItxvA+fX1CtbGFhgYUFkFMZPR6F1HnClHq8HyubWtJexX06CRmdt33hrd7nA7SFY4qoGpnYuOKcRykPPgDCBcsHx9Iv+fNL2PueBehCWUfYQIIMGLOCcOmXDXsh1+yCt35tUPfvzGFuSvzvoinXOxqa02qOhM6733nVP2MAdaej2XN11DPKjLZCD+yBvahGCo7JfTKAN9UD7s8Oe9zUNIhz8fWI8DG2k38WCFdxugANcXrvTVd1IEbuv3Jour7Hzn7jLMBNfKs7R3i67gRVrbeCOEDhinmWhAatsqdquM2XzHZINhK2cqTjHr/XZdVJUbgN3MWAVXKbSyg9jesRW2xP9di+lwrL5ojM3m2H/kG9hwcIA37c71W6wJdW2J2S5nrjYbq/t1AHAhJsKQeyfPvf6IMJgghPJhFZ4x0KlfLFvt22du45Au/A1SOlGc0P672XXwhLtOcM0kTTEMMd0qkVmMNXxMd/tsedUjInr4SQDgOfeXMSiN0FCL5WHah4L1qqYXPJOJlttd+a5M+YpcG5poLYKQ5f+6JJ4r8bbJYP47hq4r7QAs9PjYNhHJd4o8l5taiwuOpa7AS4XKqI/5NjJbTnaWK92nLdLuhQAJayRNMiygXPBeQN+Qbvu0zDc3y+aUzhbkGR73sI7ljvUnndx2q3t+X8CDAD66FtrIL864AAAAABJRU5ErkJggg==)](/feed.html)

- 上一篇：[要聊天，先付费    ](http://www.ruanyifeng.com/blog/2016/05/group-chat.html)
- 下一篇：[DNS 原理入门   ](http://www.ruanyifeng.com/blog/2016/06/dns.html)

分类：

- [开发者手册](http://www.ruanyifeng.com/blog/developer/)

- [⇐ ](http://www.ruanyifeng.com/blog/2016/05/group-chat.html)
- [ ⇒](http://www.ruanyifeng.com/blog/2016/06/dns.html)

# CSS Modules 用法教程

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

作者： [阮一峰](http://www.ruanyifeng.com)

日期： [2016年6月10日](http://www.ruanyifeng.com/blog/2016/06/)

[![珠峰培训](http://www.ruanyifeng.com/blog/images/sponsor_zhufeng5.png)](http://www.zhufengpeixun.cn/main/course/guide.html?ref=ruanyifeng.com)

学过网页开发就会知道，CSS 不能算编程语言，只是网页样式的一种描述方法。

为了让 CSS 也能适用软件工程方法，程序员想了各种办法，让它变得像一门编程语言。从最早的Less、SASS，到后来的 PostCSS，再到最近的 CSS in JS，都是为了解决这个问题。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016061001.png)

本文介绍的 [CSS Modules](https://github.com/css-modules/css-modules) 有所不同。它不是将 CSS 改造成编程语言，而是功能很单纯，只加入了局部作用域和模块依赖，这恰恰是网页组件最急需的功能。

因此，CSS Modules 很容易学，因为它的规则少，同时又非常有用，可以保证某个组件的样式，不会影响到其他组件。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016061002.png)

## 零、示例库

我为这个教程写了一个[示例库](https://github.com/ruanyf/css-modules-demos)，包含六个Demo。通过它们，你可以轻松学会CSS Modules。

首先，克隆示例库。

>     
>     $ git clone https://github.com/ruanyf/css-modules-demos.git
>     

然后，安装依赖。

>     
>     $ cd css-modules-demos
>     $ npm install
>     

接着，就可以运行第一个示例了。

>     
>     $ npm run demo01
>     

打开浏览器，访问`http://localhost:8080`，查看结果。其他示例的运行方法类似。

## 一、局部作用域

CSS的规则都是全局的，任何一个组件的样式规则，都对整个页面有效。

产生局部作用域的唯一方法，就是使用一个独一无二的`class`的名字，不会与其他选择器重名。这就是 CSS Modules 的做法。

下面是一个React组件[`App.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo01/components/App.js)。

>     
>     import React from 'react';
>     import style from './App.css';
>     
>     export default ()=>{return(<h1 className={style.title}>
>           Hello World
>         </h1>);};

上面代码中，我们将样式文件[`App.css`](https://github.com/ruanyf/css-modules-demos/blob/master/demo01/components/App.css)输入到`style`对象，然后引用`style.title`代表一个`class`。

>     .title {color: red;}

构建工具会将类名`style.title`编译成一个哈希字符串。

>     <h1class="_3zyde4l1yATCOkgn-DBWEL">
>       Hello World
>     </h1>

`App.css`也会同时被编译。

>     ._3zyde4l1yATCOkgn-DBWEL {color: red;}

这样一来，这个类名就变成独一无二了，只对`App`组件有效。

CSS Modules 提供各种[插件](https://github.com/css-modules/css-modules/blob/master/docs/get-started.md)，支持不同的构建工具。本文使用的是 Webpack 的[`css-loader`](https://github.com/webpack/css-loader#css-modules)插件，因为它对 CSS Modules 的支持最好，而且很容易使用。顺便说一下，如果你想学 Webpack，可以阅读我的教程[`Webpack-Demos`](https://github.com/ruanyf/webpack-demos)。

下面是这个示例的[`webpack.config.js`](https://github.com/ruanyf/css-modules-demos/blob/master/demo01/webpack.config.js)。

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

### 文档信息

- 版权声明：自由转载-非商用-非衍生-保持署名（[创意共享3.0许可证](http://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)）
- 发表日期： 2016年6月10日
- 更多内容： [ 档案](http://www.ruanyifeng.com/blog/archives.html)  » 
[ 开发者手册](http://www.ruanyifeng.com/blog/developer/)
- 博客文集：[《前方的路》](http://road.ruanyifeng.com)，[《未来世界的幸存者》](http://survivor.ruanyifeng.com)
- 社交媒体：[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAYAAACNiR0NAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAk1JREFUeNqsVc9rE0EU/mZ3dhPNJl2bVIk/Km09aFBE8GLvnrwJXvwLxIsgCP4Fnit6E8Gb0IMHwUsL9SSNgiAoooJIpE1Joo1h82uT7IxvxmRN3Q32kAdvdrI773vfe+/bDTu9WioDcDAda3Ja8piepQ1avCkCeny0Y+R9KenKwOmHHLvPaKn7AtVOoO8dOWDCMpg+41gMQv5FNEJACgoE8MsPNLDBhgfoutMOsJDmWLmU037C4TApciljwQ/kHoohQxV06+wMXNvE7WINuaSpvdYVKLgWnl3O4zAxU3Z1IYVGT+B5qYWV9z2kbQaT/cOwTsxOUUYF+mB5Dkmi8HG3h2q9hxsFNwRTdvQgxxnXRrMvIdkEhllis/qtiWuLDm4WZnBlPoWnXz28LHdw0uGR7m9Wu3j0qYGEubfn4UlBfXO4gTZltRNMg9w9f0i7kNFxllsBlS0x75gYfxyWTBUjT2W5CSMSPBrQuG21+hiMDS8CeCzF8eSLp13uQ3Ab1IqMFZN8tFHPmgOBF99bYP8Be1Xp6t7OJszJgKpPSiZvaj7uf2hguz2IBQuozDvFH6RDBjuK9wdQDvt0nMpW+8efGyh5UcAeZb2+UcHbnz5Jx4wdlp4yJYU3kLiQtfBwOYeLc8nIwfXtNu69q2Oz4mMxbemYOOOjKarhvq51KUjg3GwiFPIuvcNF6pnSnWK0lOEabNLgQh1aJFAhlGB9rG110B2+oyRNPc0sZbRNFltmLKDKqj4Qrm1ojzOxDz2pyPQ0P7CK4c40/wJ+CzAAGYrXsvfFXR4AAAAASUVORK5CYII=) twitter](https://twitter.com/ruanyf)，[![](data:image/png;base64,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) weibo](http://weibo.com/ruanyf)
- Feed订阅： [![](data:image/gif;base64,R0lGODlhFAAUANU2APV1GfmrePZ8IeR5VPq2ieNkLf7p3NpFJveCJ/NoFfibVPR1IexiJfvdzuZrNfXGuOhUEueTevaFOfzIpNxDGeZZJNU6IOubifiVTfOnid1aLuZpLOFSJf/28vJtIvGcefaLSd5kNu9iFv/z6//48//t4uFfLfNkCeJNGuGNc/rCof/+/PVxEeldI/V5KeKMbu9nIvB2OvzQtNxMKfOPXP///wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH5BAEAADYALAAAAAAUABQAAAb/QJstEjKZCsjCZsl0pIS2QWXaYsA8noVWIEAgFoNhhWNyMESi7Jbr/aZCFdRnZJAFJCwAt+vlOkwtEBk1hDUkExJ6bQJaGyYMLTQTDSOFHQF8jAseSFYiJwkuAQ2FE1xaHjBIMDAgARguJwABJIQTLJswDEgeIgSEJQQILAqVNQEiui1HHgkBhTUGCiwYtR0xLS0VJhtaEgoEBoQkGCfPNSoQY9xaCwAsCBPALgmkJA4cZN0CAAgY/PJqEIDwgVAECjM0bOAnwcAKGQJclKhRgoGDDjUeUDigkN8vQiBOfByAglSDAxw3IBCgYEU0FyJoEPpA4UGNDjMsaHDQR8EdPVYOMmQYQGHAhQgHLIRIsWAlgASsGMRBMWMGBQtYZ7yIsoBRKkhjOMxAiXJGGCEpHGxIYsSIhrcaQmy1EQQAOw==)](/feed.html)

[![一灯学堂](http://www.ruanyifeng.com/blog/images/sup_yideng_201711a.jpg)](http://www.yidengxuetang.com/recruit?utm_source=ruanyifeng.com)

[![优达学城](http://www.ruanyifeng.com/blog/images/sup_udacity_201711c.jpg)](https://cn.udacity.com/course/react-nanodegree--nd019-cn/?utm_source=ruanyfc&amp;utm_medium=KOL&amp;utm_campaign=react)

## 相关文章

- **2017.11.15: [Bash 脚本 set 命令教程](http://www.ruanyifeng.com/blog/2017/11/bash-set.html)**

                              服务器的开发和管理离不开 Bash 脚本，掌握它需要学习大量的细节。

                           

- **2017.11.02: [双因素认证（2FA）教程](http://www.ruanyifeng.com/blog/2017/11/2fa-tutorial.html)**

                              所谓认证（authentication）就是确认用户的身份，是网站登录必不可少的步骤。

                           

- **2017.10.24: [CSS 框架 Bulma 教程](http://www.ruanyifeng.com/blog/2017/10/bulma.html)**

                              网页样式需要大量时间开发，最省事的方法就是使用 CSS 框架。

                           

- **2017.10.11: [开源许可证教程](http://www.ruanyifeng.com/blog/2017/10/open-source-license-tutorial.html)**

                              作为一个开发者，如果你打算开源自己的代码，千万不要忘记，选择一种开源许可证（license）。

                           

## 广告[（购买广告位）](/support.html)

[![妙味课堂](http://www.ruanyifeng.com/blog/images/sup_miaov_201711.jpg)](http://www.miaov.com/index.php/example/exampleList?utm_source=ruanyifeng&amp;)

[![腾讯课堂](http://www.ruanyifeng.com/blog/images/sup_qqke_20171202.png)](https://ke.qq.com/next/index.html?from=175763)

## 留言（45条）

小俞

 说：
                

阮大师真是高产

2016年6月10日 11:31
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-357412)
 | [引用](#comment-text)

zhaozhiming

 说：
                

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

2017年12月 4日 12:44
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-382968)
 | [引用](#comment-text)

patrick

 说：
                

>     引用chjiyun的发言：
> 
> 
> 请问各位大哥大姐CSSModule转换了keyframes动画名怎么破，：global 也没用啊。

同求解

2017年12月14日 18:38
 | [#](http://www.ruanyifeng.com/blog/2016/06/css_modules.html#comment-383240)
 | [引用](#comment-text)

## 我要发表看法

您的留言
                    （HTML标签部分可用）

您的大名：

 «-必填

电子邮件：

 «-必填，不公开

个人网址：

 «-我信任你，不会填写广告链接

记住个人信息？

**正在发表您的评论，请稍候**

 «- 点击按钮

[微博](http://weibo.com/ruanyf) | [推特](https://twitter.com/ruanyf) | [GitHub](https://github.com/ruanyf)

2017 © [我的邮件](/contact.html) |

  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-46829782-1', 'ruanyifeng.com');
  ga('send', 'pageview');

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

document.getElementById("share_button").innerHTML=document.getElementById("share_button_proto").innerHTML;

X

选择其他平台 >>
分享到

[分享到...](http://www.bshare.cn/intro)[X](X)

[
Facebook
](javascript:;)

[
Twitter
](javascript:;)

[
新浪微博
](javascript:;)

[微信](javascript:;)

[腾讯微博](javascript:;)

[豆瓣网](javascript:;)

[饭否](javascript:;)

[雪球](javascript:;)

[电子邮件](javascript:;)

[Google+](javascript:;)

[QQ空间](javascript:;)

[QQ好友](javascript:;)

[Instapaper](javascript:;)

[美味书签](javascript:;)

更多平台... (133)

[bShare](http://www.bshare.cn)

#### 参考 ####

