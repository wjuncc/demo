---
layout: post
title:  "React Radium Demo7"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##

## Effect ##

![1](https://i.imgur.com/fHYmNBv.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  

local directory below:

powershell
```powershell
cd E:\n\learn\react\css\Radium\demo7
npm start
```

File index.js:

```javascript 
import React from 'react';
import { render } from 'react-dom';
import Radium, {StyleRoot} from 'radium';

class Button extends React.Component {
    render() {
        return (
            <div>
                <div key="one" style={[styles.both, styles.one]} />
                <div key="two" style={[styles.both, styles.two]} />
            </div>
        );
    }
}
Button = Radium(Button);

var styles = {
    both: {
        backgroundColor: 'black',
        border: 'solid 1px white',
        height: 100,
        width: 100
    },
    one: {
        ':hover': {
            backgroundColor: 'blue',
        }
    },
    two: {
        ':hover': {
            backgroundColor: 'red',
        }
    }
};

class App extends React.Component {
    render() {
        return (
            <StyleRoot>
                <Button>按钮</Button>
            </StyleRoot>
        );
    }
}
render(<App></App>, document.querySelector('#container'));
```

File index.html:
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
            height: 29px;
        }
    </style>
</head>
<body>
    <div id="container"></div>
</body>
</html>
```

## POST ## 

### Styling multiple elements in a single component ###
"Radium allows you to style multiple elements in the same component. You just have to give each element that has browser state modifiers like :hover or media queries a unique key or ref attribute:"

means the eact elements unlimitly.
```javascript
// Inside render
return (
  <div>
    <div key="one" style={[styles.both, styles.one]} />
    <div key="two" style={[styles.both, styles.two]} />
  </div>
);

var styles = {
  both: {
    background: 'black',
    border: 'solid 1px white',
    height: 100,
    width: 100
  },
  one: {
    ':hover': {
      background: 'blue',
    }
  },
  two: {
    ':hover': {
      background: 'red',
    }
  }
};
```