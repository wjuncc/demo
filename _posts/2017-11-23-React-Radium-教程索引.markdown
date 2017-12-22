---
layout: post
title:  "React Radium 教程索引"
date:   2017-11-23 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #

example code form [CSS IN JS,享受JS的一切 - 木杉的博客](http://mushanshitiancai.github.io/2016/12/21/js/CSS-IN-JS-享受JS的一切/)

### Notes:   ###

* i use es6 not es7, only es7 support decorator , so the terminal throw out an  error about @radium  when compile. so i delete @radium. 
* meanwhile the propType statements throw an error , so i delete this:

```javascript
	static propTypes = {
	kind: React.PropTypes.oneOf(['primary', 'warning']).isRequired
	};
```

effect:  
![1](https://i.imgur.com/85Oktq0.gif)

### Source Code ###
local directory:

>

File index.js:

```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
class Button extends React.Component {
    render() {
        return (
            <button
                style={[
                    styles.base,
                    styles[this.props.kind]
                ]}>
                {this.props.children}
            </button>
        );
    }
}

Button = Radium(Button);

var styles = {
    base: {
        color:"#dddddd",
        background: '#d90005',
        // 添加:hover伪类，是不是不能再简单了。。。
        // 可以使用:hover, :focus, :active, or @media
        ':hover': {
            background: '#cdd900'
        },
        ':active': {
            background: '#2472b1'
        }
    },
    primary: {
        background: '#0074D9',
        color:"#dddddd"
    },
    warning: {
        background: '#FF4136',
        color:"#dddddd"
    }
};

render(<Button>按钮</Button>, document.querySelector('#container'));
```

index.html

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        button{
            width:100px;
            height: 29px;
        }
    </style>
</head>
<body>
    <div id="container">ABC</div>
</body>
</html>
```


### FAULT ###
本机地址：

>    E:\n\learn\react\css\css-in-js-master\radium

执行：

	cd E:\n\learn\react\css\css-in-js-master\radium
	npm install
	
执行：
	
	npm install radium  --save-dev

执行：

	npm run-script build
	npm start


"build": "webpack ./button.js bundle.js"  什么意思



#### 参考 ####

* [Radium Intro](http://chentsulin.github.io/radium-intro/#/)
* [在Meteor中使用Radium的方法](http://www.59m59s.com/blog/zai-meteorzhong-shi-yong-radiumde-fang-fa/)
* [Radium - holly的博客](http://holly-juan.github.io/blog/技术/2014/09/28/radium.html)
* [谈谈 CSS Modules](http://boke.io/tan-tan-css-modules/)
* [React处理项目中的CSS样式--React教程中文网 - 打造国内领先的react学习网站-react教程,react学习,react培训,react开](http://www.reactpeixun.com/reactganhuo/2017-03-19/284.html)
* [CSS 模块 - 怡红院落 - SegmentFault](https://segmentfault.com/a/1190000003130731)
* [CSS Modules 详解及 React 中实践](https://zhuanlan.zhihu.com/purerender/20495964)
* [CSS in React - 通过示例学习最好的框架 - React开发社区 - CTOLib码库](https://java.ctolib.com/joeshub-css-in-react.html)
* [CSS in React - 通过示例学习最好的框架 - React开发 - 教程 - CTOLib码库](https://java.ctolib.com/article/wiki/42569)
* [CSS Modules 入门及 React 中实践 - AlloyTeam](http://www.alloyteam.com/2017/03/getting-started-with-css-modules-and-react-in-practice/)
* [React优化性能的经验教训 - 简书](https://www.jianshu.com/p/7a6072664371)
* [全栈React: 第9天 样式 - web前端资讯，web前端最新技术，web前端教程，web前端入门 - 螺钉课堂 - 可能是最好的IT自学网站-web前端-UI设计-php开发-java开发](http://nodeing.com/article/414)