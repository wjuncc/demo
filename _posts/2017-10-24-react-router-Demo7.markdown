---
layout: post
title:  "react router Demo7"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/07-more-nesting)

### Note: ###



### Effect ###

![](https://i.imgur.com/3e2An0V.gif)

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\07-more-nesting
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
import Repo from './modules/Repo'

render((
  <Router history={hashHistory}>
    <Route path="/" component={App}>
        <Route path="/repos" component={Repos}>
            <Route path="/repos/:userName/:repoName" component={Repo}/>
        </Route>
      <Route path="/repos/:userName/:repoName" component={Repo}/>
      <Route path="/about" component={About}/>
    </Route>
  </Router>
), document.getElementById('app'))

```
index.css
```css
.active {
  color: green;
}
  
```

index.html
```html  
<!doctype html public="storage">
<html>
<meta charset=utf-8/>
<title>My First React Router App</title>
<link rel=stylesheet href=index.css>
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
// modules/NavLink.js
import React from 'react'
import { Link } from 'react-router'

export default React.createClass({
  render() {
    return <Link {...this.props} activeClassName="active"/>
  }
})

```

modules/Repo.js
```javascript 
import React from 'react'

export default React.createClass({
  render() {
    return (
      <div>
        <h2>{this.props.params.repoName}</h2>
      </div>
    )
  }
})

```
modules/Repos.js
```javascript 
import React from 'react'
import { Link } from 'react-router'
import NavLink from './NavLink'

export default React.createClass({
  render() {
    return (
        <div>
            <h2>Repos</h2>
            <ul>
                <li><NavLink to="/repos/reactjs/react-router">React Router</NavLink></li>
                <li><NavLink to="/repos/facebook/react">React</NavLink></li>
            </ul>
            {/* will render `Repo.js` when at /repos/:userName/:repoName */}
            {this.props.children}
        </div>
    )
  }
})

```


## POST ##

# More Nesting

Notice how the list of links to different repositories goes away when we
navigate to a repository? What if we want the list to persist, just like
the global navigation persists?

Try to figure that out before reading on.

...

First, nest the `Repo` route under the `Repos` route. Then go render
`this.props.children` in `Repos`.

```js
// index.js
// ...
<Route path="/repos" component={Repos}>
  <Route path="/repos/:userName/:repoName" component={Repo}/>
</Route>
```

```js
// Repos.js
// ...
<div>
  <h2>Repos</h2>
  <ul>
    <li><Link to="/repos/reactjs/react-router">React Router</Link></li>
    <li><Link to="/repos/facebook/react">React</Link></li>
  </ul>
  {/* will render `Repo.js` when at /repos/:userName/:repoName */}
  {this.props.children}
</div>
```

## Active Links

Let's bring in our `NavLink` from before so we can add the `active`
class name to these links:

```js
// modules/Repos.js
// import it
import NavLink from './NavLink'

// ...
<li><NavLink to="/repos/reactjs/react-router">React Router</NavLink></li>
<li><NavLink to="/repos/facebook/react">React</NavLink></li>
// ...
```

Notice how both the `/repos` link up top and the individual repo links are
both active? When child routes are active, so are the parents.

---

[Next: Index Routes](../08-index-routes/)