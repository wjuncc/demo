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
### Styling one element depending on another's state ###
"You can query Radium's state using Radium.getState. This allows you to style or render one element based on the state of another, e.g. showing a message when a button is hovered."

A strange function. We dont need to add previous code in front of return statement any more, for coding in radium. Maybe it could reduced the code of state.

```javascript
// Inside render
return (
  <div>
    <button key="keyForButton" style={[styles.button]}>Hover me!</button>
    {Radium.getState(this.state, 'keyForButton', ':hover') ? (
      <span>{' '}Hovering!</span>
    ) : null}
  </div>
);

var styles = {
  button: {
    // Even though we don't have any special styles on the button, we need
    // to add empty :hover styles here to tell Radium to track this element's
    // state.
    ':hover': {}
  }
};
```
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
Want to add a style selector within your component? Need to pass properties to the html and body elements or group selectors (e.g. h1, h2, h3) that share properties? Radium has you covered with the <Style /> component - read how to use it here.

