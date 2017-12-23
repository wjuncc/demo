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



original post said:"... create a fictional `<Button>` component. 
have a set of default styles, will adjust its appearance based on modifiers, and will include hover, focus, and active states." 

so, without styles attribute, it have default styles.

which means, at 1st ,it just button tags and child only, not style attribute define.


```javascript
class Button extends React.Component {
  render() {
    return (
      <button>
        {this.props.children}
      </button>
    );
  }
}
```

and the old code is:

```javascript
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
```
then introduce two way to convert a simple react component to Radium component in es6

```javascript
class Button extends React.Component {
  // ...
}
module.exports = Radium(Button);
```

```javascript
// or
class Button extends React.Component {
  // ...
}
Button = Radium(Button);
```

the original post said, "...Radium resolves nested style objects into a flat object that can be applied directly to a React element. ..."  
which means, radium can convert nested objects of css inline style to flat object.  it means, we can write code in nested form, and will be convert autoly to flat by radium.

"...If you're not familiar with handling inline styles in React, see the React guide to the subject [here](https://reactjs.org/docs/dom-elements.html#style)."  
maybe i need to take a look, but not now.

"...A basic style object looks like this:"
