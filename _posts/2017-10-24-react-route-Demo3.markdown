---
layout: post
title:  "react route Demo3"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/03-navigating-with-link)

### Note: ###



### Effect ###

![](https://i.imgur.com/toQ9CKt.gif)

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\03-navigating-with-link
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
    <Route path="/" component={App}/>
    <Route path="/repos" component={Repos}/>
    <Route path="/about" component={About}/>
  </Router>
), document.getElementById('app'))

```

index.html
```html  
<!doctype html public "storage">
<html>
<meta charset=utf-8/>
<title>My First React Router App</title>
<div id=app></div>
<script src="bundle.js"></script>

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

export default React.createClass({
    render() {
        return (
            <div>
              <h1>React Router Tutorial</h1>
              <ul role="nav">
                <li><Link to="/about">About</Link></li>
                <li><Link to="/repos">Repos</Link></li>
              </ul>
            </div>
        )
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

# Navigating with Link

Perhaps the most used component in your app is `Link`. It's almost
identical to the `<a/>` tag you're used to except that it's aware of
the `Router` it was rendered in.

Let's create some navigation in our `App` component.

```js
// modules/App.js
import React from 'react'
import { Link } from 'react-router'

export default React.createClass({
  render() {
    return (
      <div>
        <h1>React Router Tutorial</h1>
        <ul role="nav">
          <li><Link to="/about">About</Link></li>
          <li><Link to="/repos">Repos</Link></li>
        </ul>
      </div>
    )
  }
})
```

Now visit [http://localhost:8080](http://localhost:8080) and click the links, click back, click
forward. It works!

---

[Next: Nested Routes](../04-nested-routes/)