---
layout: post
title:  "React Radium Demo8"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##

## Effect ##

![1](https://i.imgur.com/U9oov4q.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  

local directory below:

powershell
```powershell
cd E:\n\learn\react\css\Radium\demo8
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
                <button key="keyForButton" style={[styles.button]}>Hover me!</button>
                {Radium.getState(this.state, 'keyForButton', ':hover') ? (
                    <span>{' '}Hovering!</span>
                ) : null}
            </div>
        );
    }
}
Button = Radium(Button);

var styles = {
    button: {
        // Even though we don't have any special styles on the button, we need
        // to add empty :hover styles here to tell Radium to track this element's
        // state.
        ':hover': {}
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