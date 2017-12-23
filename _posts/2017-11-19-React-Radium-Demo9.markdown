---
layout: post
title:  "React Radium Demo9"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##
Next:[api](https://github.com/FormidableLabs/radium/tree/master/docs/api)

## Effect ##

![1](https://i.imgur.com/rmqoBRs.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  

local directory below:

powershell
```powershell
cd E:\n\learn\react\css\Radium\demo9
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
            <button style={styles.button}>
                {this.props.children}
            </button>
        );
    }
}
Button = Radium(Button);

var styles = {
    button: {
        background: ['rgba(255, 255, 255, .5)', '#fff']
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
### Fallback values ###
Sometimes you need to provide an additional value for a single CSS property in case the first one isn't applied successfully. Simply pass an array of values, and Radium will test them and apply the first one that works:

```javascript
var styles = {
  button: {
    background: ['rgba(255, 255, 255, .5)', '#fff']
  }
};
```
Is equivalent to the following CSS (note that the order is reversed):

```javascript
.button {
  background: #fff;
  background: rgba(255, 255, 255, .5);
}
```
### <Style> component ###
Want to add a style selector within your component? Need to pass properties to the html and body elements or group selectors (e.g. h1, h2, h3) that share properties? Radium has you covered with the <Style /> component - read how to use it [here](https://github.com/FormidableLabs/radium/tree/master/docs/api#style-component).

