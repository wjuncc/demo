---
layout: post
title:  "React Radium 实例2"
date:   2017-11-17 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #

example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)

### Notes:   ###

* very clear, with es6 code:

effect:  
![1](https://i.imgur.com/85Oktq0.gif)

### Source Code ###
IDE: Webstorm 2017.1.4  
local directory:

```javascript
cd E:\n\learn\react\css\Radium\demo2
npm start
```

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


### NOTES ###

twe way to import module:

```javascript
var Radium = require('radium');

// or
import Radium from 'radium'
```
and, less usage:
```javascript
import Radium, { Style } from 'radium'
```