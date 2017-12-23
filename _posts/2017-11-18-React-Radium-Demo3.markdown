---
layout: post
title:  "React Radium Demo3"
date:   2017-11-18 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)



## Note ##
Neither foreign language nor native language, if i did not take insight into each paragraph, i cound not catch the key of knowleadge.

## Effect ##

![1](https://i.imgur.com/Lj9hQzS.png)   
a static image without transition effect. Just render a blue button in radium-style code. 


### Source Code ###
IDE: Webstorm 2017.1.4  
![1](https://i.imgur.com/N6xJG3h.png)  
local directory below:
powershell
```powershell
cd E:\n\learn\react\css\Radium\demo3
npm start
```

File index.js:
```import React from 'react';
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
        background: 'blue',
        border: 0,
        borderRadius: 4,
        color: 'white',
        padding: '1.5em'
    },

    block: {
        background: 'red',
        display: 'block'
    }
};
render(<Button block="true">按钮</Button>, document.querySelector('#container'));
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


### Modifiers ###

"Radium provides one shorthand for dealing with styles that are modified by your props or state...."   
a shorthand, means the nickname, means one suits of css object code could be presented by a shortname.

"... You can pass an array of style objects to the style attribute, and they will be merged together intelligently (:hover states, for instance, will merge instead of overwrite). "   
smart? how does it do?

"...This works the same way as it does in React Native."


```javascript
<Button
  size="large"
  block={true}>
  Cool Button!
</Button>
```

"Start by adding another style to your styles object:"
add a new one named `block`:

```javascript
var styles = {
  base: {
    background: 'blue',
    border: 0,
    borderRadius: 4,
    color: 'white',
    padding: '1.5em'
  },

  block: {
    display: 'block'
  }
};
```

"Then, include that style object in the array passed to the style attribute if the conditions match:"

Just as we mentioned before, the array , is not exists in `styles` object but the  `style` attribute below:

```javascript
// Inside render
return (
  <button
    style={[
      styles.base,
      this.props.block && styles.block
    ]}>
    {this.props.children}
  </button>
);
```
change from：

```javascript
 <button style={styles.base}>
```
to：

```javascript
  <button
    style={[
      styles.base,
      this.props.block && styles.block
    ]}>
```
For the `button` tags has only one `style` attribute to store the inline style code, there is no choice but to put all information into `style` attribute either simple css default inline style, or react style object or complex radium `styles`. In other words, we can't add new style attribute likes data-style. Remember that you are  messing with new created attribute which make trouble of html translation. Merge two attributes into one is much more complex than convert one to one.
 

"Radium will ignore any elements of the array that aren't objects, such as the result of this.props.block && styles.block when this.props.block is false or undefined."

What has happened to it? Successfully we enhanced a single object to array object by  adding a pair of square brackets inside double braces.The original object becomes the first child of the array.The seconed child which follows after a comma, was composited by `Button` instance props, one bitwise operator, and `styles.block` object. The bitwise operator means the front part is a  judge statement. If `props` is true, react will apply the `styles.block` css. If false, delete `styles.block` setting. Thus we get the ability to add unlimited css unit inside `style` attribute. 

when the `block` props code is `true`:   
```javascript
render(<Button block="true">按钮</Button>, document.querySelector('#container'));
```
the color is red:  
![1](https://i.imgur.com/Lj9hQzS.png)  

when the `block` props code is `false`: 
```javascript
render(<Button block="false">按钮</Button>, document.querySelector('#container'));
```
the color is blue:   
![1](https://i.imgur.com/fA22lHB.png)   


Let i make a little change:
### Effect ###
![1](https://i.imgur.com/DJzeyrv.gif)  
Toggle the color after clicked button.

### Source Code ###
IDE: Webstorm 2017.1.4  
local directory below:
powershell
```powershell
cd E:\n\learn\react\css\Radium\demo3.1
npm start
```

File index.js:

```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';

class Button extends React.Component {
    constructor() {
        super();
        this.btnClicked = this.btnClicked.bind(this);
        this.state = {
            showRed:false
        }
    }
    btnClicked (e){
        console.log(this.setState);
        this.setState({
            showRed: !this.state.showRed
        });
    }
    render() {
        return (
            <button onClick={this.btnClicked}
                style={[
                    styles.base,
                    this.state.showRed && styles.block
                ]}>
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
    },

    block: {
        background: 'red',
        display: 'block'
    }
};
render(<Button>按钮</Button>, document.querySelector('#container'));
```



