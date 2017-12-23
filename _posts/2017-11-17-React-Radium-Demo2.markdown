---
layout: post
title:  "React Radium Demo2"
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
![1](https://i.imgur.com/fA22lHB.png)

### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  
local directory below:
powershell
```powershell
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
            <button style={styles.base}>
                {this.props.children}
            </button>
        );
    }
}

Button = Radium(Button);

var styles = {
    base: {
        background: 'blue',
        border: 0,
        borderRadius: 4,
        color: 'white',
        padding: '1.5em'
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
maybe i should to take a look, but not right now.

"...A basic style object looks like this:"

```javascript
var baseStyles = {
  background: 'blue',
  border: 0,
  borderRadius: 4,
  color: 'white',
  padding: '1.5em'
};
```
see, it's a flat object.

"We usually nest styles inside a shared styles object for easy access:"

```javascript
var styles = {
  base: {
    background: 'blue',
    border: 0,
    borderRadius: 4,
    color: 'white',
    padding: '1.5em'
  }
};
```
see, it's a nested object.

What the different between common css and radium css object? Obviously:

* no comma in front of mark in common css
* radium css object is object likes json format, ability with nested object.

"Next, simply pass your styles to the `style `attribute of an element:"

```javascript
// Inside render
return (
  <button style={styles.base}>
    {this.props.children}
  </button>
);
```

"From there, React will apply our styles to the button element. ..."  
![1](https://i.imgur.com/zSpxpWs.gif)  
yes, a blue button.

"...This is not very exciting. In fact, React does this by default, without the extra step of using Radium. "   
sure, react inline css can do this.

"...Radium becomes useful when you need to do more complex things, like handling modifiers, states, and media queries. "   
If an apperance is same all the time, we use inline style or extra css file, but, if the apperance will be changed by click,or serveral states caused by various changes, or resize browser window from mobile to PC, we use radium.

"... But, even without those complex things, Radium will still merge an array of styles and automatically apply vendor prefixes for you."

vendor prefixes means what?




