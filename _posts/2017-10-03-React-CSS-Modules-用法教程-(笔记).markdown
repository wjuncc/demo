---
layout: post
title:  "React CSS Modules 用法教程 (笔记)"
date:   2017-10-03 08:32:17 +0800
categories:  
tags:  
    - react

---

tutorial from [CSS Modules 用法教程 - 阮一峰](http://www.ruanyifeng.com/blog/2016/06/css_modules.html)

[CSS Modules](https://github.com/css-modules/css-modules) 功能单纯，仅局部作用域和模块依赖。


## 0 安装Demo

[6个Demo](https://github.com/ruanyf/css-modules-demos)  
powershell  
```powershell
cd E:\n\learn\react\css
git clone https://github.com/ruanyf/css-modules-demos.git
Rename-Item css-modules-demos ryf
cd ryftyvb
npm install

cd E:\n\learn\react\css\ryf
npm run demo01

cd E:\n\learn\react\css\ryf
Start-Process chrome.exe http://localhost:8080
```

powershell 重命名文件夹  
http://localhost:8080  
![](https://i.imgur.com/kZbfJ6o.png)


## Demo1 局部作用域
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
更多的，在radium中，style等于一个对象，title等于一个对象中的子对象。 

会编译`style.title`，同时编译css和div：

```css
<style type="text/css">._2p6G6PoaU8pET88ZnLP4VY{color:red}</style>
```
```js
<h1 data-reactroot="" class="_2p6G6PoaU8pET88ZnLP4VY">Hello World</h1>
```
注意，`class`这个值是随机值，每次启动服务都是一样的。
![](https://i.imgur.com/nO3RNPu.png)



CSS Modules 有很多[插件](https://github.com/css-modules/css-modules/blob/master/docs/get-started.md)，支持Webpack的是[`css-loader`](https://github.com/webpack/css-loader#css-modules)。

下面是的`webpack.config.js`。
webpack.config.js
```js
var webpack = require('webpack');

module.exports = {
  entry: __dirname + '/index.js',
  output: {
    publicPath: '/',
    filename: './bundle.js'
  },
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        loader: 'babel',
        query: {
          presets: ['es2015', 'stage-0', 'react']
        }
      },
      {
        test: /\.css$/,
        loader: "style-loader!css-loader?modules"
      },
    ]
  },
  plugins: [
    new webpack.optimize.UglifyJsPlugin({
      compress: { warnings: false }
    })
  ]
};

```

上面代码中，关键的一行是`style-loader!css-loader?modules`，它在`css-loader`后面加了一个查询参数`modules`，表示打开 CSS Modules 功能。

运行powershell,标题显示为红色。   
```powershell
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo01
``` 
![](https://i.imgur.com/kZbfJ6o.png)

## Demo2 全局作用域

全局`class`定义，不会被随机。
```
:global(.className)
```
加入全局`class` ，即`:global(.title)`:  
demo02/components/App.css
```css
.title {
  color: red;
}

:global(.title) {
  color: green;
}
```
正常css类写法，就是全局`class`。  注意，正常css加引号(quotes)，而编译css加大括号(brances):  
```js
import React from 'react';
import styles from './App.css';

export default () => {
  return (
    <h1 className="title">
      Hello World
    </h1>
  );
};

```

运行powershell,标题显示为绿色。
```powershell
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo02
``` 
![](https://i.imgur.com/qSU71Ix.png)

编译css的写法，可以更复杂一点，  
用冒号+函数+括号(参数)的形式，改成:local(.name)，类似:global(.name)，  
```css
:local(.className)
```
这里，杂糅了css的伪类（冒号 colon），通用函数（小括号 parentheses）。

demo02/components/App.css 
```css
:local(.title) {color: red;}
:global(.title) {color: green;}
```

![](https://i.imgur.com/kZbfJ6o.png)

## Demo3 定制哈希类名

`css-loader`默认的哈希算法是`[hash:base64]`，  
将`.title`编译成`._3zyde4l1yATCOkgn-DBWEL`。

`webpack.config.js`定制哈希字符串的格式。


```json 
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        loader: 'babel',
        query: {
          presets: ['es2015', 'stage-0', 'react']
        }
      },
      {
        test: /\.css$/,
        loader: "style-loader!css-loader?modules&localIdentName=[path][name]---[local]---[hash:base64:5]"
      },
    ]
  },
```

运行powershell,
```powershell
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo03
```  

由于设置做了修改： 
```json
loader: "style-loader!css-loader?modules"

loader: "style-loader!css-loader?modules&localIdentName=[path][name]---[local]---[hash:base64:5]"
```

对应关系是：  

* [path] => demo03/components //斜杠换成-
* [name] => App //是文件名
* [local]  => title //是css类名
* [hash:base64:5] => XSDrm //:5取开头5位数

因此结果就是： `.title`被编译成了`demo03-components-App---title---XSDrm`。

```html
<style type="text/css">.demo03-components-App---title---XSDrm{color:red}</style>

<h1 data-reactroot="" class="demo03-components-App---title---XSDrm">Hello World</h1>
```

![](https://i.imgur.com/hvCpjIB.png)

## Demo4 Class 的组合

选择器A继承选择器B，称为"组合"（["composition"](https://github.com/css-modules/css-modules#composition)）。

让`.title`继承`.className` 。 
demo04/components/App.css 
```css
.className {  background-color: blue;}
.title {  composes: className;
  color: red;
}
```

js不用修改。   
运行powershell,
```powershell
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo04
```
![](https://i.imgur.com/Q9A67sx.png)    
编译后的代码。
```html
<style type="text/css">._3dtg3JNp5iVp2oSUiZlcxm{background-color:blue}._2kGQVj0cE6MIRPU3jcAj6n{color:red}</style>


<h1 data-reactroot="" class="_2kGQVj0cE6MIRPU3jcAj6n _3dtg3JNp5iVp2oSUiZlcxm">Hello World</h1>
```

![](https://i.imgur.com/7vGBMEF.png)

## Demo5 输入其他模块
选择器继承选择器，  
前面讲的是同一个css文件中，选择器继承选择器。  
下面讲的是一个css文件中的选择器，继承另一个css文件中的选择器。 也就是说，选择器可以跨越多个css文件，不受物理文件的限制。  

local path：

demo05/components/another.css
```css
.className {background-color: green;}
```

demo05/components/App.css
```css
.title {
  composes: className from './another.css';
  color: red;
}
```

运行powershell,
```
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo05
```
绿色的背景上的红色标题。  

![](https://i.imgur.com/NwIUL7r.png)


## Demo6 输入变量

安装 PostCSS 和 [postcss-modules-values](https://github.com/css-modules/postcss-modules-values)。让 css-Module 支持使用变量  

运行powershell,
```powershell
cd E:\n\learn\react\css\ryf
npm install --save postcss-loader postcss-modules-values
``` 

把`postcss-loader`加入[`webpack.config.js`]demo06/webpack.config.js
```js
var webpack = require('webpack');
var values = require('postcss-modules-values');

module.exports = {
  entry: __dirname + '/index.js',
  output: {
    publicPath: '/',
    filename: './bundle.js'
  },
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        loader: 'babel',
        query: {
          presets: ['es2015', 'stage-0', 'react']
        }
      },
      {
        test: /\.css$/,
        loader: "style-loader!css-loader?modules!postcss-loader"
      },
    ]
  },
  postcss: [
    values
  ],
  plugins: [
    new webpack.optimize.UglifyJsPlugin({
      compress: { warnings: false }
    })
  ]
}; 
``` 

demo06/components/colors.css 定义变量。
```css
@value blue: #0c77f8;
@value red: #ff0000;
@value green: #aaf200;
```

demo06/components/App.css引用变量
```css
@value colors: "./colors.css";
@value blue, red, green from colors;

.title {
  color: red;
  background-color: blue;
}
```


运行powershell,
```powershell
Start-Process chrome.exe http://localhost:8080
cd E:\n\learn\react\css\ryf
npm run demo06
```

蓝色的背景上有一个红色的`h1`。
![](https://i.imgur.com/R3YddlN.png)

（完）
