---
layout: post
title:  "React Radium 实例3"
date:   2017-11-18 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium #


example code form [Using Radium, radium's guide page in git](https://github.com/FormidableLabs/radium/tree/master/docs/guides)

Neither foreign language nor native language, if i did not take insight into each paragraph, i cound not catch the key of knowleadge.

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

What has happened to it? Successfully we enhanced a single object to array object by  adding a pair of square brackets inside the braces.The original object becomes the first child of the array.The seconed child which follows after a comma, was composited by `Button` instance props, one bitwise operator, and `styles.block` object. The bitwise operator means the front part is a  judge statement. If `props` is true, will apply the `styles.block` css. If false, delete `styles.block` setting. Thus we get the ability to add unlimited css unit inside the array. 

### Browser States ###
Radium supports styling for three browser states that are targeted with pseudo-selectors in normal CSS: :hover, :focus, and :active.

To add styles for these states, add a special key to your style object with the additional rules:

Pseudo-selectors is a special. Leave the out , let me diving into the question why we need to add quotation marks outside key? In fact , the style object's key could add quotes mark likes:
```
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
but as easy to write, we dont do it like that. 

In css file, any words in front of open brace  could be treated as name correctly. But in Javascript file, colon marks means the split the key and the value in key-value data liks object either json, and `@` means `decorator` in es7.The quotye marks have a guaranty of having the keyname compiled correctly.                                                                          											

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

Nested browser states
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
Known issues with media queries
IE9 Support
IE9 supports CSS media queries, but doesn't support the matchMedia API. You'll need a polyfill that includes addListener.

Styling multiple elements in a single component
Radium allows you to style multiple elements in the same component. You just have to give each element that has browser state modifiers like :hover or media queries a unique key or ref attribute:

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
Styling one element depending on another's state
You can query Radium's state using Radium.getState. This allows you to style or render one element based on the state of another, e.g. showing a message when a button is hovered.

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

