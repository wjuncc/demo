---
layout: post
title:  "react router Demo5"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/05-active-links)

### Note: ###



### Effect ###

![]()

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\05-active-links
npm install
Start-Process chrome.exe http://localhost:8080/
npm start
```
index.js
```javascript 
import React from 'react'
import { render } from 'react-dom'
import { Router, Route, hashHistory } from 'react-router'
import App from './modules/App'
import About from './modules/About'
import Repos from './modules/Repos'

render((
  <Router history={hashHistory}>
    <Route path="/" component={App}>
      <Route path="/repos" component={Repos}/>
      <Route path="/about" component={About}/>
    </Route>
  </Router>
), document.getElementById('app'))
```

index.css
```javascript 
.active {
    color: green;
}
```
index.html
```html  

<!doctype html public "storage">
<html>
<meta charset=utf-8/>
<title>My First React Router App</title>
<div id=app></div>
<script src="bundle.js"></script>
<link rel="stylesheet" href="index.css" />
```

modules/About.js
```javascript 
import React from 'react'

export default React.createClass({
  render() {
    return <div>About</div>
  }
})

```

modules/App.js
```javascript 
import React from 'react'
import { Link } from 'react-router'
import NavLink from './NavLink'

export default React.createClass({
  render() {
    return (
      <div>
        <h1>React Router Tutorial</h1>
        <ul role="nav">
            <li><NavLink to="/about">About</NavLink></li>
            <li><NavLink to="/repos">Repos</NavLink></li>
        </ul>
        {this.props.children}
      </div>
    )
  }
})

```
modules/NavLink.js
```javascript 
import React from 'react'
import { Link } from 'react-router'

export default React.createClass({
    render() {
        return <Link {...this.props} activeClassName="active"/>
    }
})
```
modules/Repos.js
```javascript 
import React from 'react'

export default React.createClass({
  render() {
    return <div>Repos</div>
  }
})

```




## POST ##

# Active Links

One way that `Link` is different from `a` is that it knows if the path
it links to is active so you can style it differently.

## Active Styles

Let's see how it looks with inline styles, add `activeStyle` to your
`Link`s.

```js
// modules/App.js
<li><Link to="/about" activeStyle={{ color: 'red' }}>About</Link></li>
<li><Link to="/repos" activeStyle={{ color: 'red' }}>Repos</Link></li>
```

Now as you navigate, the active link is red.
![](https://i.imgur.com/ozwVn8c.gif)
## Active Class Name

You can also use an active class name instead of inline-styles.

```js
// modules/App.js
<li><Link to="/about" activeClassName="active">About</Link></li>
<li><Link to="/repos" activeClassName="active">Repos</Link></li>
```

We don't have a stylesheet on the page yet though. Lets add one-extra
point if you can add a `link` tag from memory.

```html
// index.html
<link rel="stylesheet" href="index.css" />
```

And the CSS file:

```css
.active {
  color: green;
}
```

You'll need to manually refresh the browser since Webpack isn't building
our `index.html`.


And the actived link is green now:  
![](https://i.imgur.com/yeXm2Zb.gif)
## Nav Link Wrappers

Most links in your site don't need to know they are active, usually just
primary navigation links need to know. It's useful to wrap those so you
don't have to remember what your `activeClassName` or `activeStyle` is
everywhere.


means only navigation need change present in each page.


We will use a spread operator here, the three dots. It clones our props
and in this use case it clones `activeClassName` to our desired component for
us to benefit from.

Create a new file at `modules/NavLink.js` that looks like this:

```js
// modules/NavLink.js
import React from 'react'
import { Link } from 'react-router'

export default React.createClass({
  render() {
    return <Link {...this.props} activeClassName="active"/>
  }
})
```

Now you can go change your links to `NavLink`s.

```js
// modules/App.js
import NavLink from './NavLink'

// ...

<li><NavLink to="/about">About</NavLink></li>
<li><NavLink to="/repos">Repos</NavLink></li>
```

Oh, how beautiful upon the renders is the composability of components.

---

[Next: Params](../06-params/)