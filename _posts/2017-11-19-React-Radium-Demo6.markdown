---
layout: post
title:  "React Radium Demo6"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##

## Effect ##

![1](https://i.imgur.com/3zv2XCo.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  

local directory below:

powershell
```powershell
cd E:\n\learn\react\css\Radium\demo6
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
                    style
                ]}>
                {this.props.children}
            </button>
        );
    }
}
Button = Radium(Button);

var style = {
    width: '25%',
    '@media (min-width: 320px)': {
        width: '100%',
        ':hover': {
            backgroundColor: 'white'
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
#### Nested browser states ####
Media query styles can also contain nested browser states:

```javascript
var style = {
  width: '25%',

  '@media (min-width: 320px)': {
    width: '100%',

    ':hover': {
      background: 'white'
    }
  }
};
```
#### Known issues with media queries ####
##### IE9 Support #####
"IE9 supports CSS media queries, but doesn't support the matchMedia API. You'll need a polyfill that includes addListener."

ignore IE9!
