---
layout: post
title:  "React Radium Demo4"
date:   2017-11-19 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)


## Note ##

## Effect ##

![1](https://i.imgur.com/afu0BkZ.gif)    


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  
local directory below:
powershell
```powershell
cd E:\n\learn\react\css\Radium\demo4
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
                    this.props.block && styles.block
                ]}>
                {this.props.children}
            </button>
        );
    }
}

Button = Radium(Button);

var styles = {
    base: {
        backgroundColor: 'blue',
        border: 0,
        borderRadius: 4,
        color: 'white',
        padding: '1.5em',
        ':hover': {
            backgroundColor: 'red'
        },
        ':focus': {
            backgroundColor: 'green'
        },
        ':active': {
            backgroundColor: 'yellow'
        },
    },
    block: {
        display: 'block',

        ':hover': {
            boxShadow: '0 3px 0 rgba(0,0,0,0.2)'
        }
    },
};
render(<Button block="true">按钮</Button>, document.querySelector('#container'));
```

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
### Browser States ###
Radium supports styling for three browser states that are targeted with pseudo-selectors in normal CSS: :hover, :focus, and :active.

To add styles for these states, add a special key to your style object with the additional rules:

Pseudo-selectors is a special. Leave the post out, let me diving into the question why we need to add quotation marks outside key? In fact , we could add quotes mark outside keys likes:

```javascript
var styles = {
  'base': {
    'background': 'blue',
    'border': 0,
    'borderRadius': 4,
    'color': 'white',
    'padding': '1.5em',

    ':hover': {
      'backgroundColor': 'red'
    },
  }
}
```
For coding handy, we don't do it like that. We don't add quotation marks positively until it caused error.

In css file, any words in front of open brace  could be treated as css name correctly. But javascript's rule is quite differ from css. In javascript file, colon is a separator to depart the key and the value in key-value data likes object and json data, and `@` means `decorator` in es7. The quotation marks(eithor single quotation or double one) have a guaranty of having the key-name compiled correctly.   	

```javascript
var styles = {
  base: {
    background: 'blue',
    border: 0,
    borderRadius: 4,
    color: 'white',
    padding: '1.5em',

    ':hover': {
      backgroundColor: 'red'
    },

    ':focus': {
      backgroundColor: 'green'
    },

    ':active': {
      backgroundColor: 'yellow'
    },
  },

  block: {
    display: 'block',

    ':hover': {
      boxShadow: '0 3px 0 rgba(0,0,0,0.2)'
    }
  },
};
```
Radium will merge styles for any active states when your component is rendered.
