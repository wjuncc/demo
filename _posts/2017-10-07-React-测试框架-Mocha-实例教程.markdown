---
layout: post
title:  "React 测试框架 Mocha 实例教程"
date:   2017-10-07 11:35:17 +0800
categories:  
tags: 
    - react

---
测试框架 Mocha 实例教程 - 阮一峰的网络日志a.bshareDiv,#bsPanel,#bsMorePanel,#bshareF{border:none;background:none;padding:0;margin:0;font:12px Helvetica,Calibri,Tahoma,Arial,宋体,sans-serif;line-height:14px;}#bsPanel div,#bsMorePanel div,#bshareF div{display:block;}.bsRlogo .bsPopupAwd,.bsRlogoSel .bsPopupAwd,.bsLogo .bsPopupAwd,.bsLogoSel .bsPopupAwd{line-height:16px !important;}a.bshareDiv div,#bsFloatTab div{*display:inline;zoom:1;display:inline-block;}a.bshareDiv img,a.bshareDiv div,a.bshareDiv span,a.bshareDiv a,#bshareF table,#bshareF tr,#bshareF td{text-decoration:none;background:none;margin:0;padding:0;border:none;line-height:1.2}a.bshareDiv span{display:inline;float:none;}div.buzzButton{cursor:pointer;font-weight:bold;}.buzzButton .shareCount a{color:#333}.bsStyle1 .shareCount a{color:#fff}span.bshareText{white-space:nowrap;}span.bshareText:hover{text-decoration:underline;}a.bshareDiv .bsPromo,div.bshare-custom .bsPromo{display:none;position:absolute;z-index:100;}a.bshareDiv .bsPromo.bsPromo1,div.bshare-custom .bsPromo.bsPromo1{width:51px;height:18px;top:-18px;left:0;line-height:16px;font-size:12px !important;font-weight:normal !important;color:#fff;text-align:center;background:url(//static.bshare.cn/frame/images/bshare_box_sprite2.gif) no-repeat 0 -606px;}div.bshare-custom .bsPromo.bsPromo2{background:url(//static.bshare.cn/frame/images/bshare_promo_sprite.gif) no-repeat;cursor:pointer;}.bsBox{display:none;z-index:100000001;font-size:12px;background:url(//static.bshare.cn/frame/images//background-opaque-dark.gif) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}.bsClose{_overflow:hidden;cursor:pointer;position:absolute;z-index:10000000;color:#666;font-weight:bold;font-family:Helvetica,Arial;font-size:14px;line-height:20px;}.bsTop{color:#666;background:#f2f2f2;height:24px;line-height:24px;border-bottom:1px solid #e8e8e8;}.bsTop span{float:left;}.bsFrameDiv,#bsMorePanel{border:none;background:#fff;}.bsReturn{float:right;*margin-right:20px;margin-right:36px;text-align:right;cursor:pointer;line-height:24px;color:#666;opacity:0.5;}#bsReturn:hover{text-decoration:underline;opacity:1;}div.bsClear{clear:both;height:0;line-height:0;overflow:hidden;font-size:0;}.bsSearchDiv{padding:5px 15px;background-color:#fafafa;}.bFind-wrapper-top{background:#fff;border-color:#ccc #aaa #aaa #ccc;border-style:solid;border-width:1px;height:16px;padding:4px;margin:0;}.bFind-wrapper-top input{padding:0 !important;border:none !important;box-shadow:none !important;line-height:16px !important;}.bFind-placeholder{background:url("//static.bshare.cn/css/images/search-icon.gif") no-repeat;display:block;float:left;height:16px;width:16px;}.bFind{background:none;border:none;float:left;font-size:11px !important;height:16px !important;margin-left:3px;outline:none;padding:0;width:400px;}.bsPlatDiv{height:322px;background:#fff;overflow:auto;padding:0 15px;}#bsLogoList{display:block;list-style:none;overflow:hidden;margin:0;padding:0;}#bsLogoList li{float:left;display:inline-block;width:71px;text-align:center;font-size:12px;height:80px;margin:0 !important;}#bsLogoList .bsPlatIcon{cursor:pointer;display:block !important;text-align:center;}#bsLogoList .bsPlatImg{width:32px;height:32px;border:none !important;display:inline-block;}#bsLogoList .bsPlatImg:hover{-moz-border-radius:7px;-webkit-border-radius:7px;border-radius:7px;box-shadow:0 0 15px #a7a8ac;}#bsLogoList .bsPlatName{white-space:nowrap;text-overflow:ellipsis;overflow:hidden;text-align:center;color:#333 !important;margin-top:2px;line-height:140%;*width:70px;}#bsLogoList .bsPromoM{text-align:center;}.bsFooterDiv{height:24px;line-height:24px;padding:0 15px;border-top:1px solid #e8e8e8;background:#f2f2f2;text-align:right;}a.bsLogoLink{color:#666;}.bsLogoLink:hover{text-decoration:underline;}.bsPromoM{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;}.bsNew,.bsHot,.bsRec,.bsAwd{background-position:0 -552px;width:19px;margin:5px auto 1px;line-height:16px;height:18px;font-size:12px;color:#fff;overflow:hidden;}.bsNew{background-position:0 -570px;}.bsRec{width:30px;background-position:0 -588px;}.bsAwd{background:url(//static.bshare.cn/frame/images//promot/promote.gif) no-repeat;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}
if (/mobile/i.test(navigator.userAgent) || /android/i.test(navigator.userAgent)) document.body.classList.add('mobile');

window.addEventListener('load', function(event) {
  setTimeout(function () {
    hab('#sup-post-2');
    hab('#gd1-inner');
  }, 1000);
});

阮一峰的网络日志  » [首页](http://www.ruanyifeng.com/blog/) » [档案](http://www.ruanyifeng.com/blog/archives.html)

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAABGdBTUEAAK/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAUzSURBVHjavFdbbFRVFF3nPjoz7dTWTittaW0jUDRAUqaNojyqREnEQKgfUj9MqqAmhqRt/OCD4CuY+Kckoh+aiGKC+gMJbdHoRysJ8dkhhmJLNdDKtJU+6GMK87j3Hs85d2Z6HzNtMYWb3Dn3NWftvfba+5xNYDl+e6Fkj6yqb/oDRbWq14vlPBLRKCITkxf0ROLt+hNjp1PPSRK4kA3vF1dXNRcWlyA2OQU9eos9opAkAiKxD+XkKO6t15aRWO7J/MgmAZU8MEgexgZHMX518Dh72sYMmVKShnxWuWHdHtxKIDIYTgMuDzgfmSOIQkYMpdUF8OY92Hytt4/jvkg47czzU16iQovM3QFwmNck+Yyduu7D6NA0Z6JR4THntFs9V4tWQg6Ui3s6MwKDncsFTnXKLJhDSeUK3AgPtyhccDzmVs999buRt/1Vm4i0od+hX7+MRG87jPGB/w1u8FPj9xEw7McVrnYuOCvtpjTth3J/nTg99c8LRhKhr6D3dTB5R24bXFwbMXBsyZzeoXaycEpJ95TB09AGX/NpqLVNtw8urnVzLvHjFNxiFqRy2OOHuqUVnue+ACkoWzo4O6lGzTmuHq6nPvY2m9rVqjrIK2rMEKxqyG5NPAKt+wjo0LklgfNxJkZMA3KJvqRUk3z5UFY3QH14P0h+WUY79HPvgv7VuSg4ZRGY1YgZgqXmORccF17sy2ehnf9AeO085K2HQFbtXBScj0LcpgF2cN+WV+DZ/LJQu6gD4R7oV7pBJwbSgtMvfiPoVp56DySwxm7EtkMs1WdAB7qzggsDJKQYsHucSkOudrkiCPWR/fA2nYCn8SNIK4NptSMyAu3sAdDRkIsJdfth0LzSrODUoPNZ4KI9SxJI5UHk7D4GdQfz2us31c7CoHMjRkKuDPHseCMrONVhNcDJwMJpKFVvg9L4OaTiNWm1x789KCqkrXhVBiEz0WYCT2nAzQAD1/vaETv1GrRfP4Vx5cfMNcDPwvP0h0DhanPym7OIf/+O67vcJ1/PCJ4KgdzaUP6Wz+dU+5yIL6fV+PsHGAOdwlPpvvUOyeeAVGyCdqkDNB6DPjsBSrnndfOGevOh3RhGItxvA+fX1CtbGFhgYUFkFMZPR6F1HnClHq8HyubWtJexX06CRmdt33hrd7nA7SFY4qoGpnYuOKcRykPPgDCBcsHx9Iv+fNL2PueBehCWUfYQIIMGLOCcOmXDXsh1+yCt35tUPfvzGFuSvzvoinXOxqa02qOhM6733nVP2MAdaej2XN11DPKjLZCD+yBvahGCo7JfTKAN9UD7s8Oe9zUNIhz8fWI8DG2k38WCFdxugANcXrvTVd1IEbuv3Jour7Hzn7jLMBNfKs7R3i67gRVrbeCOEDhinmWhAatsqdquM2XzHZINhK2cqTjHr/XZdVJUbgN3MWAVXKbSyg9jesRW2xP9di+lwrL5ojM3m2H/kG9hwcIA37c71W6wJdW2J2S5nrjYbq/t1AHAhJsKQeyfPvf6IMJgghPJhFZ4x0KlfLFvt22du45Au/A1SOlGc0P672XXwhLtOcM0kTTEMMd0qkVmMNXxMd/tsedUjInr4SQDgOfeXMSiN0FCL5WHah4L1qqYXPJOJlttd+a5M+YpcG5poLYKQ5f+6JJ4r8bbJYP47hq4r7QAs9PjYNhHJd4o8l5taiwuOpa7AS4XKqI/5NjJbTnaWK92nLdLuhQAJayRNMiygXPBeQN+Qbvu0zDc3y+aUzhbkGR73sI7ljvUnndx2q3t+X8CDAD66FtrIL864AAAAABJRU5ErkJggg==)](/feed.html)

- 上一篇：[读懂 ECMAScri](http://www.ruanyifeng.com/blog/2015/11/ecmascript-specification.html)
- 下一篇：[常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

分类：

- [JavaScript](http://www.ruanyifeng.com/blog/javascript/)

- [⇐ ](http://www.ruanyifeng.com/blog/2015/11/ecmascript-specification.html)
- [ ⇒](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

# 测试框架 Mocha 实例教程

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

作者： [阮一峰](http://www.ruanyifeng.com)

日期： [2015年12月 3日](http://www.ruanyifeng.com/blog/2015/12/)

[![珠峰培训](http://www.ruanyifeng.com/blog/images/sponsor_zhufeng5.png)](http://www.zhufengpeixun.cn/main/course/guide.html?ref=ruanyifeng.com)

[`Mocha`](https://mochajs.org/)（发音"摩卡"）诞生于2011年，是现在最流行的JavaScript测试框架之一，在浏览器和Node环境都可以使用。

所谓"测试框架"，就是运行测试的工具。通过它，可以为JavaScript应用添加测试，从而保证代码的质量。

本文全面介绍如何使用`Mocha`，让你轻松上手。如果你以前对测试一无所知，本文也可以当作JavaScript单元测试入门。值得说明的是，除了Mocha以外，类似的测试框架还有[`Jasmine`](http://jasmine.github.io/)、[`Karma`](http://karma-runner.github.io/)、[`Tape`](https://github.com/substack/tape/)等，也很值得学习。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120301.png)

## 一、安装

我为本文写了一个示例库[`Mocha-demos`](https://github.com/ruanyf/mocha-demos)，请先安装这个库。

>     
>     $ git clone https://github.com/ruanyf/mocha-demos.git
>     

如果你的电脑没装Git，可以直接下载[zip压缩包](https://github.com/ruanyf/mocha-demos/archive/master.zip)，进行解压。

然后，进入[`mocha-demos`](https://github.com/ruanyf/mocha-demos)目录，安装依赖（你的电脑必须有Node）。

>     
>     $ cd mocha-demos
>     $ npm install
>     

上面代码会在目录内部安装`Mocha`，为了操作的方便，请在全面环境也安装一下`Mocha`。

>     
>     $ npm install --global mocha
>     

## 二、测试脚本的写法

`Mocha`的作用是运行测试脚本，首先必须学会写测试脚本。所谓"测试脚本"，就是用来测试源码的脚本。

下面是一个加法模块[`add.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo01/add.js)的代码。

>     
>     // add.js
>     functionadd(x, y){return x + y;}
>     
>     module.exports = add;

要测试这个加法模块是否正确，就要写测试脚本。

通常，测试脚本与所要测试的源码脚本同名，但是后缀名为`.test.js`（表示测试）或者`.spec.js`（表示规格）。比如，`add.js`的测试脚本名字就是[`add.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo01/add.test.js)。

>     
>     // add.test.js
>     var add =require('./add.js');var expect =require('chai').expect;describe('加法函数的测试',function(){it('1 加 1 应该等于 2',function(){expect(add(1,1)).to.be.equal(2);});});

上面这段代码，就是测试脚本，它可以独立执行。测试脚本里面应该包括一个或多个`describe`块，每个`describe`块应该包括一个或多个`it`块。

`describe`块称为"测试套件"（test suite），表示一组相关的测试。它是一个函数，第一个参数是测试套件的名称（"加法函数的测试"），第二个参数是一个实际执行的函数。

`it`块称为"测试用例"（test case），表示一个单独的测试，是测试的最小单位。它也是一个函数，第一个参数是测试用例的名称（"1 加 1 应该等于 2"），第二个参数是一个实际执行的函数。

## 三、断言库的用法

上面的测试脚本里面，有一句断言。

>     expect(add(1,1)).to.be.equal(2);

所谓"断言"，就是判断源码的实际执行结果与预期结果是否一致，如果不一致就抛出一个错误。上面这句断言的意思是，调用`add(1, 1)`，结果应该等于2。

所有的测试用例（it块）都应该含有一句或多句的断言。它是编写测试用例的关键。断言功能由断言库来实现，Mocha本身不带断言库，所以必须先引入断言库。

>     var expect =require('chai').expect;

断言库有很多种，Mocha并不限制使用哪一种。上面代码引入的断言库是[`chai`](http://chaijs.com/)，并且指定使用它的[`expect`](http://chaijs.com/api/bdd/)断言风格。

`expect`断言的优点是很接近自然语言，下面是一些例子。

>     
>     // 相等或不相等
>     expect(4+5).to.be.equal(9);expect(4+5).to.be.not.equal(10);expect(foo).to.be.deep.equal({ bar:'baz'});
>     // 布尔值为true
>     expect('everthing').to.be.ok;expect(false).to.not.be.ok;
>     // typeof
>     expect('test').to.be.a('string');expect({ foo:'bar'}).to.be.an('object');expect(foo).to.be.an.instanceof(Foo);
>     // include
>     expect([1,2,3]).to.include(2);expect('foobar').to.contain('foo');expect({ foo:'bar', hello:'universe'}).to.include.keys('foo');
>     // empty
>     expect([]).to.be.empty;expect('').to.be.empty;expect({}).to.be.empty;
>     // match
>     expect('foobar').to.match(/^foo/);

基本上，`expect`断言的写法都是一样的。头部是`expect`方法，尾部是断言方法，比如`equal`、`a`/`an`、`ok`、`match`等。两者之间使用`to`或`to.be`连接。

如果`expect`断言不成立，就会抛出一个错误。事实上，只要不抛出错误，测试用例就算通过。

>     it('1 加 1 应该等于 2',function(){});

上面的这个测试用例，内部没有任何代码，由于没有抛出了错误，所以还是会通过。

## 四、Mocha的基本用法

有了测试脚本以后，就可以用Mocha运行它。请进入[`demo01`](https://github.com/ruanyf/mocha-demos/tree/master/demo01)子目录，执行下面的命令。

>     
>     $ mocha add.test.js
>     
>       加法函数的测试
>         ✓ 1 加 1 应该等于 21 passing (8ms)

上面的运行结果表示，测试脚本通过了测试，一共只有1个测试用例，耗时是8毫秒。

`mocha`命令后面紧跟测试脚本的路径和文件名，可以指定多个测试脚本。

>     
>     $ mocha file1 file2 file3
>     

Mocha默认运行`test`子目录里面的测试脚本。所以，一般都会把测试脚本放在`test`目录里面，然后执行`mocha`就不需要参数了。请进入[`demo02`](https://github.com/ruanyf/mocha-demos/tree/master/demo02)子目录，运行下面的命令。

>     
>     $ mocha
>     
>       加法函数的测试
>         ✓ 1 加 1 应该等于 2
>         ✓ 任何数加0应该等于自身
>     
>       2 passing (9ms)

这时可以看到，`test`子目录里面的测试脚本执行了。但是，你打开`test`子目录，会发现下面还有一个`test/dir`子目录，里面还有一个测试脚本[`multiply.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo02/test/dir/multiply.test.js)，并没有得到执行。原来，Mocha默认只执行`test`子目录下面第一层的测试用例，不会执行更下层的用例。

为了改变这种行为，就必须加上`--recursive`参数，这时`test`子目录下面所有的测试用例----不管在哪一层----都会执行。

>     
>     $ mocha --recursive
>     
>       加法函数的测试
>         ✓ 1 加 1 应该等于 2
>         ✓ 任何数加0应该等于自身
>     
>       乘法函数的测试
>         ✓ 1 乘 1 应该等于 13 passing (9ms)

## 五、通配符

命令行指定测试脚本时，可以使用通配符，同时指定多个文件。

>     
>     $ mocha spec/{my,awesome}.js
>     $ mocha test/unit/*.js
>     

上面的第一行命令，指定执行`spec`目录下面的`my.js`和`awesome.js`。第二行命令，指定执行`test/unit`目录下面的所有js文件。

除了使用Shell通配符，还可以使用Node通配符。

>     
>     $ mocha 'test/**/*.@(js|jsx)'

上面代码指定运行`test`目录下面任何子目录中、文件后缀名为`js`或`jsx`的测试脚本。注意，Node的通配符要放在单引号之中，否则星号（`*`）会先被Shell解释。

上面这行Node通配符，如果改用Shell通配符，要写成下面这样。

>     
>     $ mocha test/{,**/}*.{js,jsx}

## 六、命令行参数

除了前面介绍的`--recursive`，Mocha还可以加上其他命令行参数。请在[`demo02`](https://github.com/ruanyf/mocha-demos/tree/master/demo02)子目录里面，运行下面的命令，查看效果。

### 6.1 --help, -h

`--help`或`-h`参数，用来查看Mocha的所有命令行参数。

>     
>     $ mocha --help
>     

### 6.2 --reporter, -R

`--reporter`参数用来指定测试报告的格式，默认是`spec`格式。

>     
>     $ mocha
>     # 等同于
>     $ mocha --reporter spec
>     

除了`spec`格式，官方网站还提供了其他许多[报告格式](http://mochajs.org/#reporters)。

>     
>     $ mocha --reporter tap
>     
>     1..2
>     ok 1 加法函数的测试 1 加 1 应该等于 2
>     ok 2 加法函数的测试 任何数加0应该等于自身
>     # tests 2
>     # pass 2
>     # fail 0
>     

上面是`tap`格式报告的显示结果。

`--reporters`参数可以显示所有内置的报告格式。

>     
>     $ mocha --reporters
>     

使用[`mochawesome`](http://adamgruber.github.io/mochawesome/)模块，可以生成漂亮的HTML格式的报告。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120303.png)

>     
>     $ npm install --save-dev mochawesome
>     $ ../node_modules/.bin/mocha --reporter mochawesome
>     

上面代码中，`mocha`命令使用了项目内安装的版本，而不是全局安装的版本，因为`mochawesome`模块是安装在项目内的。

然后，测试结果报告就在[`mochaawesome-reports`](https://github.com/ruanyf/mocha-demos/blob/master/demo02/mochawesome-reports)子目录生成。

### 6.3 --growl, -G

打开[`--growl`](http://growl.info/)参数，就会将测试结果在桌面显示。

>     
>     $ mocha --growl
>     

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120304.png)

### 6.4 --watch，-w

`--watch`参数用来监视指定的测试脚本。只要测试脚本有变化，就会自动运行Mocha。

>     
>     $ mocha --watch
>     

上面命令执行以后，并不会退出。你可以另外打开一个终端窗口，修改`test`目录下面的测试脚本`add.test.js`，比如删除一个测试用例，一旦保存，Mocha就会再次自动运行。

### 6.5 --bail, -b

`--bail`参数指定只要有一个测试用例没有通过，就停止执行后面的测试用例。这对[持续集成](http://www.ruanyifeng.com/blog/2015/09/continuous-integration.html)很有用。

>     
>     $ mocha --bail
>     

### 6.6 --grep, -g

`--grep`参数用于搜索测试用例的名称（即`it`块的第一个参数），然后只执行匹配的测试用例。

>     
>     $ mocha --grep "1 加 1"

上面代码只测试名称中包含"1 加 1"的测试用例。

### 6.7 --invert, -i

`--invert`参数表示只运行不符合条件的测试脚本，必须与`--grep`参数配合使用。

>     
>     $ mocha --grep "1 加 1"--invert
>     

## 七，配置文件mocha.opts

Mocha允许在`test`目录下面，放置配置文件`mocha.opts`，把命令行参数写在里面。请先进入[`demo03`](https://github.com/ruanyf/mocha-demos/tree/master/demo03)目录，运行下面的命令。

>     
>     $ mocha --recursive --reporter tap --growl
>     

上面这个命令有三个参数`--recursive`、`--reporter tap`、`--growl`。

然后，把这三个参数写入`test`目录下的[`mocha.opts`](https://github.com/ruanyf/mocha-demos/blob/master/demo03/test/mocha.opts)文件。

>     --reporter tap
>     --recursive
>     --growl
>     

然后，执行`mocha`就能取得与第一行命令一样的效果。

>     
>     $ mocha
>     

如果测试用例不是存放在test子目录，可以在`mocha.opts`写入以下内容。

>     
>     server-tests
>     --recursive
>     

上面代码指定运行`server-tests`目录及其子目录之中的测试脚本。

## 八、ES6测试

如果测试脚本是用ES6写的，那么运行测试之前，需要先用Babel转码。进入[`demo04`](https://github.com/ruanyf/mocha-demos/tree/master/demo04)目录，打开[`test/add.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo04/test/add.test.js)文件，可以看到这个测试用例是用ES6写的。

>     
>     import add from '../src/add.js';
>     import chai from 'chai';let expect = chai.expect;describe('加法函数的测试',function(){it('1 加 1 应该等于 2',function(){expect(add(1,1)).to.be.equal(2);});});

ES6转码，需要安装Babel。

>     
>     $ npm install babel-core babel-preset-es2015 --save-dev
>     

然后，在项目目录下面，新建一个[`.babelrc`](https://github.com/ruanyf/mocha-demos/blob/master/demo04/.babelrc)配置文件。

>     {"presets":["es2015"]}

最后，使用`--compilers`参数指定测试脚本的转码器。

>     
>     $ ../node_modules/mocha/bin/mocha --compilers js:babel-core/register
>     

上面代码中，`--compilers`参数后面紧跟一个用冒号分隔的字符串，冒号左边是文件的后缀名，右边是用来处理这一类文件的模块名。上面代码表示，运行测试之前，先用`babel-core/register`模块，处理一下`.js`文件。由于这里的转码器安装在项目内，所以要使用项目内安装的Mocha；如果转码器安装在全局，就可以使用全局的Mocha。

下面是另外一个例子，使用Mocha测试CoffeeScript脚本。测试之前，先将`.coffee`文件转成`.js`文件。

>     
>     $ mocha --compilers coffee:coffee-script/register
>     

注意，Babel默认不会对Iterator、Generator、Promise、Map、Set等全局对象，以及一些全局对象的方法（比如`Object.assign`）转码。如果你想要对这些对象转码，就要安装`babel-polyfill`。

>     
>     $ npm install babel-polyfill --save
>     

然后，在你的脚本头部加上一行。

>     
>     import 'babel-polyfill'

## 九、异步测试

Mocha默认每个测试用例最多执行2000毫秒，如果到时没有得到结果，就报错。对于涉及异步操作的测试用例，这个时间往往是不够的，需要用`-t`或`--timeout`参数指定超时门槛。

进入[`demo05`](https://github.com/ruanyf/mocha-demos/tree/master/demo05)子目录，打开测试脚本[`timeout.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo05/timeout.test.js)。

>     it('测试应该5000毫秒后结束',function(done){var x =true;var f =function(){
>         x =false;expect(x).to.be.not.ok;done(); // 通知Mocha测试结束
>     };setTimeout(f,4000);});

上面的测试用例，需要4000毫秒之后，才有运行结果。所以，需要用`-t`或`--timeout`参数，改变默认的超时设置。

>     
>     $ mocha -t 5000 timeout.test.js
>     

上面命令将测试的超时时限指定为5000毫秒。

另外，上面的测试用例里面，有一个`done`函数。`it`块执行的时候，传入一个`done`参数，当测试结束的时候，必须显式调用这个函数，告诉Mocha测试结束了。否则，Mocha就无法知道，测试是否结束，会一直等到超时报错。你可以把这行删除试试看。

Mocha默认会高亮显示超过75毫秒的测试用例，可以用`-s`或`--slow`调整这个参数。

>     
>     $ mocha -t 5000-s 1000 timeout.test.js
>     

上面命令指定高亮显示耗时超过1000毫秒的测试用例。

下面是另外一个异步测试的例子[`async.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo05/async.test.js)。

>     it('异步请求应该返回一个对象',function(done){
>       request
>         .get('[https://api.github.com](https://api.github.com)').end(function(err, res){expect(res).to.be.an('object');done();});});

运行下面命令，可以看到这个测试会通过。

>     
>     $ mocha -t 10000 async.test.js
>     

另外，Mocha内置对Promise的支持，允许直接返回Promise，等到它的状态改变，再执行断言，而不用显式调用`done`方法。请看[`promise.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo05/promise.test.js)。

>     it('异步请求应该返回一个对象',function(){returnfetch('[https://api.github.com](https://api.github.com)').then(function(res){return res.json();}).then(function(json){expect(json).to.be.an('object');});});

## 十、测试用例的钩子

Mocha在`describe`块之中，提供测试用例的四个钩子：`before()`、`after()`、`beforeEach()`和`afterEach()`。它们会在指定时间执行。

>     describe('hooks',function(){before(function(){ // 在本区块的所有测试用例之前执行
>     });after(function(){ // 在本区块的所有测试用例之后执行
>     });beforeEach(function(){ // 在本区块的每个测试用例之前执行
>     });afterEach(function(){ // 在本区块的每个测试用例之后执行
>     }); // test cases
>     });

进入[`demo06`](https://github.com/ruanyf/mocha-demos/tree/master/demo06)子目录，可以看到下面两个例子。首先是`beforeEach`的例子[`beforeEach.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo06/beforeEach.test.js)。

>     
>     // beforeEach.test.js
>     describe('beforeEach示例',function(){var foo =false;beforeEach(function(){
>         foo =true;});it('修改全局变量应该成功',function(){expect(foo).to.be.equal(true);});});

上面代码中，`beforeEach`会在`it`之前执行，所以会修改全局变量。

另一个例子[`beforeEach-async.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo06/beforeEach-async.test.js)则是演示，如何在`beforeEach`之中使用异步操作。

>     
>     // beforeEach-async.test.js
>     describe('异步 beforeEach 示例',function(){var foo =false;beforeEach(function(done){setTimeout(function(){
>           foo =true;done();},50);});it('全局变量异步修改应该成功',function(){expect(foo).to.be.equal(true);});});

## 十一、测试用例管理

大型项目有很多测试用例。有时，我们希望只运行其中的几个，这时可以用`only`方法。`describe`块和`it`块都允许调用`only`方法，表示只运行某个测试套件或测试用例。

进入[`demo07`](https://github.com/ruanyf/mocha-demos/tree/master/demo07)子目录，测试脚本[`test/add.test.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo07/test/add.test.js)就使用了`only`。

>     
>     it.only('1 加 1 应该等于 2',function(){expect(add(1,1)).to.be.equal(2);});it('任何数加0应该等于自身',function(){expect(add(1,0)).to.be.equal(1);});

上面代码中，只有带有`only`方法的测试用例会运行。

>     
>     $ mocha test/add.test.js
>     
>       加法函数的测试
>         ✓ 1 加 1 应该等于 21 passing (10ms)

此外，还有`skip`方法，表示跳过指定的测试套件或测试用例。

>     
>     it.skip('任何数加0应该等于自身',function(){expect(add(1,0)).to.be.equal(1);});

上面代码的这个测试用例不会执行。

## 十二、浏览器测试

除了在命令行运行，Mocha还可以在浏览器运行。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120305.png)

首先，使用`mocha init`命令在指定目录生成初始化文件。

>     
>     $ mocha init demo08
>     

运行上面命令，就会在[`demo08`](https://github.com/ruanyf/mocha-demos/tree/master/demo08)目录下生成[`index.html`](https://github.com/ruanyf/mocha-demos/blob/master/demo08/index.html)文件，以及配套的脚本和样式表。

>     
>     <!DOCTYPE html>
>     <html>
>       <body>
>         <h1>Unit.js tests in the browser with Mocha</h1>
>         <div id="mocha"></div>
>         <script src="mocha.js"></script>
>         <script>
>           mocha.setup('bdd');
>         </script>
>         <script src="tests.js"></script>
>         <script>
>           mocha.run();
>         </script>
>       </body>
>     </html>
>     

然后，新建一个源码文件[`add.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo08/add.js)。

>     
>     // add.js
>     functionadd(x, y){return x + y;}

然后，把这个文件，以及断言库`chai.js`，加入`index.html`。

>     
>     <script>
>       mocha.setup('bdd');
>     </script>
>     <script src="add.js"></script>
>     <script src="http://chaijs.com/chai.js"></script>
>     <script src="tests.js"></script>
>     <script>
>       mocha.run();
>     </script>
>     

最后，在[`tests.js`](https://github.com/ruanyf/mocha-demos/blob/master/demo08/tests.js)里面写入测试脚本。

>     var expect = chai.expect;describe('加法函数的测试',function(){it('1 加 1 应该等于 2',function(){expect(add(1,1)).to.be.equal(2);});it('任何数加0等于自身',function(){expect(add(1,0)).to.be.equal(1);expect(add(0,0)).to.be.equal(0);});});

现在，在浏览器里面打开`index.html`，就可以看到测试脚本的运行结果。

## 十三、生成规格文件

Mocha支持从测试用例生成规格文件。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120306.png)

进入[`demo09`](https://github.com/ruanyf/mocha-demos/tree/master/demo09)子目录，运行下面的命令。

>     
>     $ mocha --recursive -R markdown > spec.md
>     

上面命令根据`test`目录的所有测试脚本，生成一个规格文件[`spec.md`](https://github.com/ruanyf/mocha-demos/blob/master/demo09/spec.md)。`-R markdown`参数指定规格报告是markdown格式。

如果想生成HTML格式的报告[`spec.html`](https://github.com/ruanyf/mocha-demos/blob/master/demo09/spec.html)，使用下面的命令。

>     
>     $ mocha --recursive -R doc > spec.html
>     

（完）

### 文档信息

- 版权声明：自由转载-非商用-非衍生-保持署名（[创意共享3.0许可证](http://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)）
- 发表日期： 2015年12月 3日
- 更多内容： [ 档案](http://www.ruanyifeng.com/blog/archives.html)  » 
[ JavaScript](http://www.ruanyifeng.com/blog/javascript/)
- 博客文集：[《前方的路》](http://road.ruanyifeng.com)，[《未来世界的幸存者》](http://survivor.ruanyifeng.com)
- 社交媒体：[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAYAAACNiR0NAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAk1JREFUeNqsVc9rE0EU/mZ3dhPNJl2bVIk/Km09aFBE8GLvnrwJXvwLxIsgCP4Fnit6E8Gb0IMHwUsL9SSNgiAoooJIpE1Joo1h82uT7IxvxmRN3Q32kAdvdrI773vfe+/bDTu9WioDcDAda3Ja8piepQ1avCkCeny0Y+R9KenKwOmHHLvPaKn7AtVOoO8dOWDCMpg+41gMQv5FNEJACgoE8MsPNLDBhgfoutMOsJDmWLmU037C4TApciljwQ/kHoohQxV06+wMXNvE7WINuaSpvdYVKLgWnl3O4zAxU3Z1IYVGT+B5qYWV9z2kbQaT/cOwTsxOUUYF+mB5Dkmi8HG3h2q9hxsFNwRTdvQgxxnXRrMvIdkEhllis/qtiWuLDm4WZnBlPoWnXz28LHdw0uGR7m9Wu3j0qYGEubfn4UlBfXO4gTZltRNMg9w9f0i7kNFxllsBlS0x75gYfxyWTBUjT2W5CSMSPBrQuG21+hiMDS8CeCzF8eSLp13uQ3Ab1IqMFZN8tFHPmgOBF99bYP8Be1Xp6t7OJszJgKpPSiZvaj7uf2hguz2IBQuozDvFH6RDBjuK9wdQDvt0nMpW+8efGyh5UcAeZb2+UcHbnz5Jx4wdlp4yJYU3kLiQtfBwOYeLc8nIwfXtNu69q2Oz4mMxbemYOOOjKarhvq51KUjg3GwiFPIuvcNF6pnSnWK0lOEabNLgQh1aJFAhlGB9rG110B2+oyRNPc0sZbRNFltmLKDKqj4Qrm1ojzOxDz2pyPQ0P7CK4c40/wJ+CzAAGYrXsvfFXR4AAAAASUVORK5CYII=) twitter](https://twitter.com/ruanyf)，[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAYAAACNiR0NAAAACXBIWXMAAAsTAAALEwEAmpwYAAAKT2lDQ1BQaG90b3Nob3AgSUNDIHByb2ZpbGUAAHjanVNnVFPpFj333vRCS4iAlEtvUhUIIFJCi4AUkSYqIQkQSoghodkVUcERRUUEG8igiAOOjoCMFVEsDIoK2AfkIaKOg6OIisr74Xuja9a89+bN/rXXPues852zzwfACAyWSDNRNYAMqUIeEeCDx8TG4eQuQIEKJHAAEAizZCFz/SMBAPh+PDwrIsAHvgABeNMLCADATZvAMByH/w/qQplcAYCEAcB0kThLCIAUAEB6jkKmAEBGAYCdmCZTAKAEAGDLY2LjAFAtAGAnf+bTAICd+Jl7AQBblCEVAaCRACATZYhEAGg7AKzPVopFAFgwABRmS8Q5ANgtADBJV2ZIALC3AMDOEAuyAAgMADBRiIUpAAR7AGDIIyN4AISZABRG8lc88SuuEOcqAAB4mbI8uSQ5RYFbCC1xB1dXLh4ozkkXKxQ2YQJhmkAuwnmZGTKBNA/g88wAAKCRFRHgg/P9eM4Ors7ONo62Dl8t6r8G/yJiYuP+5c+rcEAAAOF0ftH+LC+zGoA7BoBt/qIl7gRoXgugdfeLZrIPQLUAoOnaV/Nw+H48PEWhkLnZ2eXk5NhKxEJbYcpXff5nwl/AV/1s+X48/Pf14L7iJIEyXYFHBPjgwsz0TKUcz5IJhGLc5o9H/LcL//wd0yLESWK5WCoU41EScY5EmozzMqUiiUKSKcUl0v9k4t8s+wM+3zUAsGo+AXuRLahdYwP2SycQWHTA4vcAAPK7b8HUKAgDgGiD4c93/+8//UegJQCAZkmScQAAXkQkLlTKsz/HCAAARKCBKrBBG/TBGCzABhzBBdzBC/xgNoRCJMTCQhBCCmSAHHJgKayCQiiGzbAdKmAv1EAdNMBRaIaTcA4uwlW4Dj1wD/phCJ7BKLyBCQRByAgTYSHaiAFiilgjjggXmYX4IcFIBBKLJCDJiBRRIkuRNUgxUopUIFVIHfI9cgI5h1xGupE7yAAygvyGvEcxlIGyUT3UDLVDuag3GoRGogvQZHQxmo8WoJvQcrQaPYw2oefQq2gP2o8+Q8cwwOgYBzPEbDAuxsNCsTgsCZNjy7EirAyrxhqwVqwDu4n1Y8+xdwQSgUXACTYEd0IgYR5BSFhMWE7YSKggHCQ0EdoJNwkDhFHCJyKTqEu0JroR+cQYYjIxh1hILCPWEo8TLxB7iEPENyQSiUMyJ7mQAkmxpFTSEtJG0m5SI+ksqZs0SBojk8naZGuyBzmULCAryIXkneTD5DPkG+Qh8lsKnWJAcaT4U+IoUspqShnlEOU05QZlmDJBVaOaUt2ooVQRNY9aQq2htlKvUYeoEzR1mjnNgxZJS6WtopXTGmgXaPdpr+h0uhHdlR5Ol9BX0svpR+iX6AP0dwwNhhWDx4hnKBmbGAcYZxl3GK+YTKYZ04sZx1QwNzHrmOeZD5lvVVgqtip8FZHKCpVKlSaVGyovVKmqpqreqgtV81XLVI+pXlN9rkZVM1PjqQnUlqtVqp1Q61MbU2epO6iHqmeob1Q/pH5Z/YkGWcNMw09DpFGgsV/jvMYgC2MZs3gsIWsNq4Z1gTXEJrHN2Xx2KruY/R27iz2qqaE5QzNKM1ezUvOUZj8H45hx+Jx0TgnnKKeX836K3hTvKeIpG6Y0TLkxZVxrqpaXllirSKtRq0frvTau7aedpr1Fu1n7gQ5Bx0onXCdHZ4/OBZ3nU9lT3acKpxZNPTr1ri6qa6UbobtEd79up+6Ynr5egJ5Mb6feeb3n+hx9L/1U/W36p/VHDFgGswwkBtsMzhg8xTVxbzwdL8fb8VFDXcNAQ6VhlWGX4YSRudE8o9VGjUYPjGnGXOMk423GbcajJgYmISZLTepN7ppSTbmmKaY7TDtMx83MzaLN1pk1mz0x1zLnm+eb15vft2BaeFostqi2uGVJsuRaplnutrxuhVo5WaVYVVpds0atna0l1rutu6cRp7lOk06rntZnw7Dxtsm2qbcZsOXYBtuutm22fWFnYhdnt8Wuw+6TvZN9un2N/T0HDYfZDqsdWh1+c7RyFDpWOt6azpzuP33F9JbpL2dYzxDP2DPjthPLKcRpnVOb00dnF2e5c4PziIuJS4LLLpc+Lpsbxt3IveRKdPVxXeF60vWdm7Obwu2o26/uNu5p7ofcn8w0nymeWTNz0MPIQ+BR5dE/C5+VMGvfrH5PQ0+BZ7XnIy9jL5FXrdewt6V3qvdh7xc+9j5yn+M+4zw33jLeWV/MN8C3yLfLT8Nvnl+F30N/I/9k/3r/0QCngCUBZwOJgUGBWwL7+Hp8Ib+OPzrbZfay2e1BjKC5QRVBj4KtguXBrSFoyOyQrSH355jOkc5pDoVQfujW0Adh5mGLw34MJ4WHhVeGP45wiFga0TGXNXfR3ENz30T6RJZE3ptnMU85ry1KNSo+qi5qPNo3ujS6P8YuZlnM1VidWElsSxw5LiquNm5svt/87fOH4p3iC+N7F5gvyF1weaHOwvSFpxapLhIsOpZATIhOOJTwQRAqqBaMJfITdyWOCnnCHcJnIi/RNtGI2ENcKh5O8kgqTXqS7JG8NXkkxTOlLOW5hCepkLxMDUzdmzqeFpp2IG0yPTq9MYOSkZBxQqohTZO2Z+pn5mZ2y6xlhbL+xW6Lty8elQfJa7OQrAVZLQq2QqboVFoo1yoHsmdlV2a/zYnKOZarnivN7cyzytuQN5zvn//tEsIS4ZK2pYZLVy0dWOa9rGo5sjxxedsK4xUFK4ZWBqw8uIq2Km3VT6vtV5eufr0mek1rgV7ByoLBtQFr6wtVCuWFfevc1+1dT1gvWd+1YfqGnRs+FYmKrhTbF5cVf9go3HjlG4dvyr+Z3JS0qavEuWTPZtJm6ebeLZ5bDpaql+aXDm4N2dq0Dd9WtO319kXbL5fNKNu7g7ZDuaO/PLi8ZafJzs07P1SkVPRU+lQ27tLdtWHX+G7R7ht7vPY07NXbW7z3/T7JvttVAVVN1WbVZftJ+7P3P66Jqun4lvttXa1ObXHtxwPSA/0HIw6217nU1R3SPVRSj9Yr60cOxx++/p3vdy0NNg1VjZzG4iNwRHnk6fcJ3/ceDTradox7rOEH0x92HWcdL2pCmvKaRptTmvtbYlu6T8w+0dbq3nr8R9sfD5w0PFl5SvNUyWna6YLTk2fyz4ydlZ19fi753GDborZ752PO32oPb++6EHTh0kX/i+c7vDvOXPK4dPKy2+UTV7hXmq86X23qdOo8/pPTT8e7nLuarrlca7nuer21e2b36RueN87d9L158Rb/1tWeOT3dvfN6b/fF9/XfFt1+cif9zsu72Xcn7q28T7xf9EDtQdlD3YfVP1v+3Njv3H9qwHeg89HcR/cGhYPP/pH1jw9DBY+Zj8uGDYbrnjg+OTniP3L96fynQ89kzyaeF/6i/suuFxYvfvjV69fO0ZjRoZfyl5O/bXyl/erA6xmv28bCxh6+yXgzMV70VvvtwXfcdx3vo98PT+R8IH8o/2j5sfVT0Kf7kxmTk/8EA5jz/GMzLdsAAAAgY0hSTQAAeiUAAICDAAD5/wAAgOkAAHUwAADqYAAAOpgAABdvkl/FRgAABPZJREFUeNqMyXtM1WUcx/FnNTdreAVCEEThyEFUrM2kwkpS05qVl8rugVpRUelaJdZaWWktdZKHssImgV04osgBCbwAa2Whm6GWoXHxcD1wHiI4t9/z/H68+wO3av1R3+217/b+CFStsHq/W2V1HW+wOmq8VkeN/E+dR/7SUSOtrmOnLc93jxA6LsTw71XLrUsHsNwHsdxl/09HGVb7QawOF1bn4ZF26QDDsmqNsH7be9psKcJs+fy/tRZjXvwM//678BVdT6BsMarhxZHeug+reW+TMC84+s0LDv4tH7PZgdXqwGrLx7yYP9KaHISOvUCwYh3+4iUMOiIJVmSMbBfy+4X581Zp/ryVfzi/FfPXd1AntxNwvkvg6zfQZ7Zg/rIV8/x7qB9fJlT/JPrcm4SOPctg3ihCR5dhNu2QQjfmSt2Yi27MRf+Uiz67Ef1TLv7Ct5CPZtMzJ4N2243Ij7Kwmjdhnt+EUZeFr/BmhvYkoBqewl8yD9/eCejGTVLoUzlSn8pBn8xBn85B/fAcf7z6PJ7rl9KdNBdP6nwuJc2jL+9+jJrXGNr1On9seZHgkQ0ESq8l4EzBOLKMod1XoE6slUKfXCd1wxp0Qxb6RBYDLzxGz8xb8aSm05u2kL4bF9N902I89yzHe986PEseoGP2YjqfvpNQeTr+4rmEKucz6LgS9f1jUuiy+VIfvxvz1GoGN99Hz8wFeGan0zl3Ae4lK3A/vJb2x7PpWPEI3bevoHfJKtypt9H1UgbDZx5E//goofJF+AtmoasWSaG2jZE6P5zg9hQ8Nyyie1Y6rQ+vpafMhdHXx7BpgjWMr7sbT5kL9/IHcUck0X3LtfgLVqAP3YAumoHeHYvaPkYKlRcudf54Bh5KpjP5Fi69tplgIMCQabK/rIxtO3bgqqxkmJHzdXbRknYbrWIcrWEJ9D8RjXaMRe2ciNo5QQr1QYRUjnC8C1Nxr1pD0O/HFwyQmZmJ3W4nLS0Nm83G+vXrsSwLgP6vS2kWo/lNjKN57gTMTyJRH0Si8iZKoXZdI5Ujkt55SXRtfBuAffv2sXLlSpxOJ9nZ2SQkJBAWFobX6wVgoPooLWI0v4hxuFeFY30ahdoVhcqLkEJ9GCV1QRTehZNxZ9wPQNGXX5KZmUlbWxspKSkIIUhPT0dZFibQvSaHJjGKxujxBHZGoT+ehPpwEsoRIYUqmCR1YTTBd2NoGxtOz4Y3CPoDrNuwnuhpU7lq/HgW3LGU5l4P2h+g55XNnBOjORM/jsH3ozGLYlAFMag90ahPI6VQxZOlKo5BOyfjey+GliljaL0uA7l9D2f37uess5KBoyfwbvmIJnsajVePouXeCIKFsZglsajiyX8pvEYKoySm33DGYTjj0OVxhEri6N84kfalY2i/NRb3AhvNN0+i9Y4wPC+H4yuMxTocjzoYj7F/ymVxI/+ryH5huKaeMVzxGK54QuXT8B+y4atIZqB8Nt6SVDzFqXi+mIO39Dp+PziHwdIZDJVOJ3gogZArHsM1BcMVj1E+BcMVe1GY38auNqqnYdQkEKpOJPBNEv7DdnyVdnwVdoYqki+bge9wCv6qFAJVyQS/mU6oJhHjSCJG9VSM6kRUfXi2GK6fJYy6+CyjNrHRqLP1GbWJ0qizSfV39Tap6qdLVW+Xqt4ujfokadRdVpvgNWpt54y6qc8MV44Sfw4An+t+Gj1AKyYAAAAASUVORK5CYII=) weibo](http://weibo.com/ruanyf)
- Feed订阅： [![](data:image/gif;base64,R0lGODlhFAAUANU2APV1GfmrePZ8IeR5VPq2ieNkLf7p3NpFJveCJ/NoFfibVPR1IexiJfvdzuZrNfXGuOhUEueTevaFOfzIpNxDGeZZJNU6IOubifiVTfOnid1aLuZpLOFSJf/28vJtIvGcefaLSd5kNu9iFv/z6//48//t4uFfLfNkCeJNGuGNc/rCof/+/PVxEeldI/V5KeKMbu9nIvB2OvzQtNxMKfOPXP///wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH5BAEAADYALAAAAAAUABQAAAb/QJstEjKZCsjCZsl0pIS2QWXaYsA8noVWIEAgFoNhhWNyMESi7Jbr/aZCFdRnZJAFJCwAt+vlOkwtEBk1hDUkExJ6bQJaGyYMLTQTDSOFHQF8jAseSFYiJwkuAQ2FE1xaHjBIMDAgARguJwABJIQTLJswDEgeIgSEJQQILAqVNQEiui1HHgkBhTUGCiwYtR0xLS0VJhtaEgoEBoQkGCfPNSoQY9xaCwAsCBPALgmkJA4cZN0CAAgY/PJqEIDwgVAECjM0bOAnwcAKGQJclKhRgoGDDjUeUDigkN8vQiBOfByAglSDAxw3IBCgYEU0FyJoEPpA4UGNDjMsaHDQR8EdPVYOMmQYQGHAhQgHLIRIsWAlgASsGMRBMWMGBQtYZ7yIsoBRKkhjOMxAiXJGGCEpHGxIYsSIhrcaQmy1EQQAOw==)](/feed.html)

[![一灯学堂](http://www.ruanyifeng.com/blog/images/sup_yideng_201711a.jpg)](http://www.yidengxuetang.com/recruit?utm_source=ruanyifeng.com)

[![优达学城](http://www.ruanyifeng.com/blog/images/sup_udacity_201711c.jpg)](https://cn.udacity.com/course/react-nanodegree--nd019-cn/?utm_source=ruanyfc&amp;utm_medium=KOL&amp;utm_campaign=react)

## 相关文章

- **2017.09.19: [《ES6 标准入门（第3版）》上市了！](http://www.ruanyifeng.com/blog/2017/09/es6_primer_3rd_edition.html)**

                              2017年6月，TC39 委员会正式发布了《ES2017 标准》。

                           

- **2017.09.07: [asm.js 和 Emscripten 入门教程](http://www.ruanyifeng.com/blog/2017/09/asmjs_emscripten.html)**

                              Web 技术突飞猛进，但是有一个领域一直无法突破 ---- 游戏。

                           

- **2017.08.09: [Koa 框架教程](http://www.ruanyifeng.com/blog/2017/08/koa.html)**

                              Node 主要用在开发 Web 应用。这决定了使用 Node，往往离不开 Web 应用框架。

                           

- **2017.04.16: [JavaScript 内存泄漏教程](http://www.ruanyifeng.com/blog/2017/04/memory-leak.html)**

                              一、什么是内存泄漏？

程序的运行需要内存。只要程序提出要求，操作系统或者运行时（runtime）就必须供给内存。

                           

## 广告[（购买广告位）](/support.html)

[![妙味课堂](http://www.ruanyifeng.com/blog/images/sup_miaov_201711.jpg)](http://www.miaov.com/index.php/example/exampleList?utm_source=ruanyifeng&amp;)

[![腾讯课堂](http://www.ruanyifeng.com/blog/images/sup_qqke_20171202.png)](https://ke.qq.com/next/index.html?from=175763)

## 留言（65条）

[zhaozhiming](http://zhaozhiming.github.io/)

 说：
                

介绍的很详细哈，请问大大有没有用过Jest这个测试框架，觉得这个怎么样？

2015年12月 3日 10:47
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353038)
 | [引用](#comment-text)

Tvvi

 说：
                

waooo~ 进实习公司，刚要求学习下 mocha ，就看到这么好的 tutorial 。谢谢峰大

2015年12月 3日 11:20
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353046)
 | [引用](#comment-text)

笔墨伺候

 说：
                

>     引用zhaozhiming的发言：
> 
> 
> 介绍的很详细哈，请问大大有没有用过Jest这个测试框架，觉得这个怎么样？

没用过，不过测试库都在这了 [http://www.awesomes.cn/repos/Applications/testings](http://www.awesomes.cn/repos/Applications/testings)

2015年12月 3日 11:28
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353047)
 | [引用](#comment-text)

snowdream

 说：
                

很全面，赞

2015年12月 3日 14:12
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353051)
 | [引用](#comment-text)

Arthur

 说：
                

How about Jasmine?

2015年12月 3日 14:33
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353052)
 | [引用](#comment-text)

clirocks

 说：
                

6.7 --invent, -i

这个地方是不是写错了，看下面是invert

2015年12月 3日 17:25
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353058)
 | [引用](#comment-text)

[石樱灯笼](http://www.catscarlet.com/)

 说：
                

感觉好复杂， 还没理解

2015年12月 3日 20:58
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353068)
 | [引用](#comment-text)

阮一峰

 说：
                

@clirocks:

谢谢指出，已经改正。

2015年12月 4日 11:01
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353079)
 | [引用](#comment-text)

joe

 说：
                

赞，写得很好

2015年12月 4日 11:37
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353082)
 | [引用](#comment-text)

Dudy

 说：
                

关于测试，一直有疑问的，会不会有薛定谔猫式的影响，也就是说，测试代码本身就可能对被测试代码产生影响

2015年12月 4日 22:14
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353090)
 | [引用](#comment-text)

刘宇清

 说：
                

>     引用Dudy的发言：
> 
> 
> 关于测试，一直有疑问的，会不会有薛定谔猫式的影响，也就是说，测试代码本身就可能对被测试代码产生影响

不会，因为测试代码定义的是输入值和对输出值的判定，在输入值、被测试代码、对输出值的判定这三者不变的情况下，任何时候得到的都会是唯一结果。

2015年12月 5日 14:55
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353101)
 | [引用](#comment-text)

zhexiu

 说：
                

Cannot find module 'babel-core/register'是什么鬼

2015年12月 8日 15:09
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353160)
 | [引用](#comment-text)

VenDream

 说：
                

获益匪浅，感谢峰大。

2015年12月 9日 11:05
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353183)
 | [引用](#comment-text)

octokyle

 说：
                

谢谢峰大。摸索中使用 Mocha 有一段时间了，用这个框架完成了现在项目的回归测试部分 (https://github.com/oracle/node-oracledb/tree/master/test)

看了您的文章，仍然觉得很有收获。谢谢！

2015年12月11日 15:02
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353222)
 | [引用](#comment-text)

scgy5555

 说：
                

阮老师 docker最近很火也是开发部署测试上线的工程化流程思想，不给大家补补课吗

2015年12月11日 17:46
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353228)
 | [引用](#comment-text)

[chenjsh36](https://github.com/chenjsh36)

 说：
                

输入 mocha --compilers js:babel-core/register时候提示错误：

 Cannot find module 'babel-core/register'

已经安装了babel-core，在目录下也确实有register.js文件，但是还是报错，请问阮老师这是什么原因呢？

2015年12月15日 17:13
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353312)
 | [引用](#comment-text)

阮一峰

 说：
                

@chenjsh36:

你试一下指定mocha的路径，或者把babel-core和es2015全局安装

$ ../node_modules/mocha/bin/mocha --compilers js:babel-core/register

2015年12月15日 19:35
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353317)
 | [引用](#comment-text)

[凡凡](http://www.fflove.top)

 说：
                

js测试有比较好的代码覆盖率检测么

2015年12月18日 14:11
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353376)
 | [引用](#comment-text)

[赵宁](http://huamomo.cn)

 说：
                

阮老师出品，必属精品，必须赞一个！

2015年12月22日 09:30
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353445)
 | [引用](#comment-text)

路人丁

 说：
                

karma不是测试框架,它需要和测试框架搭配一起用

2015年12月22日 16:45
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353459)
 | [引用](#comment-text)

黑石Jimvin 

 说：
                

好精彩，想延伸一下，Polymer 框架的WebComponentsTester工具就是基于Mocha，它只需要在命令行运行wct,就能将测试结果以html 形式直接发布到localhost 2000，并帮你打开浏览器！它将Mocha 进行了二次封装，某些场景下，使用更便捷！

2015年12月26日 13:23
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353569)
 | [引用](#comment-text)

[yanhaijing](http://yanhaijing.com)

 说：
                

不能更赞了

2016年1月12日 11:25
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353952)
 | [引用](#comment-text)

[yanhaijing](http://yanhaijing.com)

 说：
                

ie8及一下版本不支持，这个问题怎么解决 ？

2016年1月12日 18:38
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353958)
 | [引用](#comment-text)

Ca

 说：
                

感謝您的詳細解說. 

發現一些小筆誤：

1) 七，配置文件mocha.opts

```$ mocha --recursive --reporter tap --growl```

裡的 `--reporter` 與 `mocha.opts` 裡的統一會讓初學更清楚。

```

--reporter spec

--recursive

--growl```

2) 九、异步测试

'测试应该500毫秒后结束' -> '测试应该5000毫秒后结束'

(sent a pull request already)

2016年1月12日 18:40
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353959)
 | [引用](#comment-text)

[yanhaijing](http://yanhaijing.com)

 说：
                

>     引用yanhaijing的发言：
> 
> 
> ie8及一下版本不支持，这个问题怎么解决 ？

自问自答吧，换个断言库，chai不行，换下面这个可以 [https://github.com/Automattic/expect.js](https://github.com/Automattic/expect.js)

2016年1月12日 18:57
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353961)
 | [引用](#comment-text)

阮一峰

 说：
                

@Ca:

谢谢指出，已经更正。

2016年1月12日 19:22
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-353962)
 | [引用](#comment-text)

段瑜斌

 说：
                

关于timeout也可不必在命令行中输入，可为单独的用例指定

this.timeout(500);

可在describe 和 it中调用

2016年1月15日 10:44
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354006)
 | [引用](#comment-text)

赵小虎

 说：
                

您好我最近也在使用mocha写测试案例 但是在测试异步的时候 总是抱错     Error: timeout of 2000ms exceeded. Ensure the done() callback is being called in this test.

2016年1月27日 17:15
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354361)
 | [引用](#comment-text)

zhangxinwei

 说：
                

您好， 请问mocha如何优先执行某个 JS

2016年1月30日 20:15
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354395)
 | [引用](#comment-text)

guissy

 说：
                

>     引用赵小虎的发言：
> 
> 
> 您好我最近也在使用mocha写测试案例 但是在测试异步的时候 总是抱错 Error: timeout of 2000ms exceeded. Ensure the done() callback is being called in this test.

mocha 并不聪明，并不知道什么时候异步调用过程已经完成，所以需要你在代码中告诉它什么时候完成了。比如请求一个json, 只有在得到 json内容时异步才完成，此时需要在最后一行加上done() 通知mocha说异步完成了。如果在获得json过程中，可以Promise.resolve().catch(err=>done(err)). 通常done() 这里并不需要加参数，当错误时才给它一个参数。使用done是一种方法。还有更好的体验是不使用done,而是直接 return Promise().then();

2016年2月 5日 22:38
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354478)
 | [引用](#comment-text)

伟

 说：
                

阮大大，你真棒，爱你

2016年2月23日 13:15
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354627)
 | [引用](#comment-text)

[Risker](http://riskers.github.io)

 说：
                

对于测试，一直好奇，Mocha这种算是功能测试，只能测试模块。不知道能不能测试页面，就是UI测试。

2016年3月 1日 21:37
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-354716)
 | [引用](#comment-text)

可乐

 说：
                

mocha 有mock功能吗 ?类似 lest支持的mock . 感谢分享.

2016年3月16日 19:26
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-355072)
 | [引用](#comment-text)

[yaochniqkl](http://yaochiqkl.github.io)

 说：
                

谢谢阮大大

2016年4月22日 11:47
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-355821)
 | [引用](#comment-text)

Memow

 说：
                

$ mocha --recursive -R doc > spec.html

生成的html文件并不是完整的html，所以打开是乱码，可有解决办法？

2016年7月29日 11:16
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-361357)
 | [引用](#comment-text)

[Mrwaite](http://code.mrwaite.cn)

 说：
                

>     引用zhangxinwei的发言：
> 
> 
> 您好， 请问mocha如何优先执行某个 JS

我也不知到我说的对不对，但是我看到Node通配符上对于测试顺序的匹配。[grunt Globbing patterns](http://gruntjs.com/configuring-tasks#globbing-patterns)

2016年7月29日 11:41
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-361358)
 | [引用](#comment-text)

[geekwen](http://geekwen.com)

 说：
                

感谢分享，受益良多。

2016年8月 1日 10:52
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-361497)
 | [引用](#comment-text)

[CoderGLM](http://gengliming.com)

 说：
                

赞一个

2016年9月23日 14:34
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-365056)
 | [引用](#comment-text)

EdgarChen

 说：
                

clone项目，使用mochawesome模块，命令行../node_modules/.bin/mocha --reporter mochawesome后，生成了html文件，但是css，font，js目录下面的文件都是 “空的”，（还有一次只生成了HTML和json文件，没有其它目录），请问是什么原因呢？

2016年10月 7日 12:46
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-365815)
 | [引用](#comment-text)

EdgarChen

 说：
                

>     引用EdgarChen的发言：
> 
> 
> clone项目，使用mochawesome模块，命令行../node_modules/.bin/mocha --reporter mochawesome后，生成了html文件，但是css，font，js目录下面的文件都是 “空的”，（还有一次只生成了HTML和json文件，没有其它目录），请问是什么原因呢？

重新clone安装依赖就好了

2016年10月 8日 17:39
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-365905)
 | [引用](#comment-text)

[qinyang912](https://github.com/qinyang912)

 说：
                

阮大，karma不在类似框架列表里吧，karma是一个测试运行时，他不是测试框架，需要配合其他测试框架才能用。

2016年10月21日 23:55
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-366826)
 | [引用](#comment-text)

[slogeor](http://www.slogeor.com)

 说：
                

>     引用zhexiu的发言：
> 
> 
> Cannot find module 'babel-core/register'是什么鬼

因为不是全局安装的，只能在node-modules当前目录下执行命令
        

2016年10月27日 11:52
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-367166)
 | [引用](#comment-text)

[slogeor](http://www.slogeor.com)

 说：
                

>     引用Memow的发言：
> 
> 
> $ mocha --recursive -R doc > spec.html
> 
> 生成的html文件并不是完整的html，所以打开是乱码，可有解决办法？

你看下代码，没有指定字符集为uft-8
        

2016年10月27日 11:54
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-367167)
 | [引用](#comment-text)

[slogeor](http://www.slogeor.com)

 说：
                

Mocha 是功能测试，阮大什么时间给我们讲讲UI测试

2016年10月27日 11:56
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-367168)
 | [引用](#comment-text)

gaoxing

 说：
                

            阮大神，您好！

你讲的很详细，作为前端开发，一看自然明白，但是你能讲讲TDD（测试驱动开发）吗？这个市面上很少有相关资源，更没有demo,我非常迫切的想学习它，望你能写一遍和上述一样的关于TDD的博客，谢谢！

2016年11月 3日 11:13
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-367655)
 | [引用](#comment-text)

johnyang

 说：
                

使用mochawesome模块，命令行../node_modules/.bin/mocha --reporter mochawesome后，生成了html文件，但是css，font，js目录下面的文件都是 “空的”

2016年12月28日 21:24
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-371259)
 | [引用](#comment-text)

johnyang

 说：
                

6.3的截图怎么出来？

2016年12月28日 21:26
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-371260)
 | [引用](#comment-text)

superq

 说：
                

最新的留言为什么要放在后面 ，越靠前越新不是很好嘛~

2017年1月12日 13:58
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-371969)
 | [引用](#comment-text)

可乐加糖

 说：
                

写得挺全面的，学习中......

2017年2月 9日 17:12
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-372628)
 | [引用](#comment-text)

cshenger

 说：
                

最近项目要用到测试框架看了Mocha，果然是强大！！！

2017年2月10日 11:38
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-372652)
 | [引用](#comment-text)

荣威

 说：
                

感谢有你这样的前辈铺路，谢过

2017年2月16日 15:22
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-372979)
 | [引用](#comment-text)

青菜

 说：
                

../node_modules/.bin/mocha --reporter mochawesome

想问下这个命令什么意思，目的和作用是什么

2017年2月16日 19:56
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-372994)
 | [引用](#comment-text)

青菜

 说：
                

>     引用cshenger的发言：
> 
> 
> 最近项目要用到测试框架看了Mocha，果然是强大！！！

hello 你知道../node_modules/.bin/mocha --reporter mochawesome是什么意思吗，我没看懂呢

2017年2月17日 14:27
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-373020)
 | [引用](#comment-text)

dudu

 说：
                

非常棒，简单易懂。

2017年3月18日 11:24
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-375034)
 | [引用](#comment-text)

dapeng

 说：
                

mocha如何后require.js配合使用？

2017年3月20日 20:04
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-375154)
 | [引用](#comment-text)

alice

 说：
                

老师，想请教您个问题：

es测试那块，

【

最后，使用--compilers参数指定测试脚本的转码器。

$ ../node_modules/mocha/bin/mocha --compilers js:babel-core/register

】

这块不太理解，不知道在哪里操作：

我的理解是在mocha.opts里添加上 【--compilers js:babel-core/register】，但是运行测试用例会报错，不知道啥原因。

2017年4月12日 20:59
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-376223)
 | [引用](#comment-text)

[Amylee](http://no)

 说：
                

写的太棒了，这么长我竟然一气呵成的看完了，不得不说阮老师言简意赅，炉火纯青，大赞，谢谢！

2017年4月25日 21:26
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-376674)
 | [引用](#comment-text)

胡衍生

 说：
                

如何用 mocha 测试 es6的代码？  并不是用 es6写测试代码，而是用 mocha 测试 es6编写的代码！

2017年6月 1日 13:58
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-377618)
 | [引用](#comment-text)

ChaselWu

 说：
                

有一些关于 JS 测试的范式、推荐解决风格吗？来提高测试的设计。

2017年6月16日 01:43
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-377995)
 | [引用](#comment-text)

JustinYi

 说：
                

感谢老师的分享。

想咨询一下，如果mocha和react结合使用。一些方法里面比较复杂。假如说是一个alert或者打开一个弹框，如何写测试用例。

2017年6月19日 10:41
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-378049)
 | [引用](#comment-text)

bug侠

 说：
                

老师，请问测试结果中的pending是什么含义呢？

2017年7月13日 17:55
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-378679)
 | [引用](#comment-text)

赵5207

 说：
                

beforeEach是ginkgo里面的，那before哪？需要在哪儿定义

2017年8月 9日 17:47
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-379388)
 | [引用](#comment-text)

kira

 说：
                

请问用mocha能进行UI测试吗

2017年8月25日 00:00
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-379800)
 | [引用](#comment-text)

枫叶mzn

 说：
                

 文章ES6测试转码部分的 “ ../node_modules/mocha/bin/mocha --compilers js:babel-core/register”这里貌似漏了个点，应该是“ ../node_modules/mocha/.bin/mocha --compilers js:babel-core/register”

2017年10月10日 15:12
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-381121)
 | [引用](#comment-text)

小白

 说：
                

老师，您好。

关于 ES6 测试：mocha --compilers js:babel-core/register

这只针对在 test 的子目录下，我 test 下好多层，那 --recursive 该怎么来测试 ES6 的测试代码呢？

2017年10月20日 11:03
 | [#](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html#comment-381491)
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

