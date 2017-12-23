---
layout: post
title:  "React Radium Demo5"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##

## Effect ##

![1](https://i.imgur.com/moON4kf.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  

Error：
![2](https://i.imgur.com/gcIWk81.png)

* [Radium - Error: please wrap your application in the StyleRoot component](https://stackoverflow.com/questions/41446835/radium-error-please-wrap-your-application-in-the-styleroot-component)
* [Media Query crashing app ](https://github.com/FormidableLabs/radium/issues/574)

local directory below:

powershell
```powershell
cd E:\n\learn\react\css\Radium\demo5
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
            <button
                style={[
                    style.base
                ]}>
                {this.props.children}
            </button>
        );
    }
}
Button = Radium(Button);

var style = {
    base:{
        width: '25%',
        '@media (min-width: 320px)': {
            width: '100%'
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
            width:100px;
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
### Media queries ###

Add media queries to your style objects the same way as you would add browser state modifiers like :hover. The key must start with @media, and the syntax is identical to CSS:

```javascript
var style = {
  width: '25%',

  '@media (min-width: 320px)': {
    width: '100%'
  }
};
```
Radium will apply the correct styles for the currently active media queries. Top level CSS rules in your media queries will be converted to CSS and rendered in an actual <style> element with !important appended instead of being applied inline so they will work with server-side rendering. Note that you must wrap your top-level component in the <StyleRoot> component to render the Radium stylesheet. Print styles will also work as normal, since they are rendered to CSS.
