---
layout: post
title:  "react route Demo6"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/06-params)

### Note: ###



### Effect ###

![](https://i.imgur.com/mAY3n3S.gif)

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\06-params
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
            <Route path="/repos" component={Repos}/>
            {/* add the new route */}
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

export default React.createClass({
    render() {
        return (
            <div>
                <h2>Repos</h2>

                {/* add some links */}
                <ul>
                    <li><Link to="/repos/reactjs/react-router">React Router</Link></li>
                    <li><Link to="/repos/facebook/react">React</Link></li>
                </ul>

            </div>
        )
    }
})
```


## POST ##

# URL Params

Consider the following URLs:

```
/repos/reactjs/react-router
/repos/facebook/react
```

These URLs would match a route path like this:

```
/repos/:userName/:repoName
```

The parts that start with `:` are URL parameters whose values will be
parsed out and made available to route components on
`this.props.params[name]`.

## Adding a Route with Parameters

Let's teach our app how to render screens at `/repos/:userName/:repoName`.

First we need a component to render at the route, make a new file at
`modules/Repo.js` that looks something like this:

```js
// modules/Repo.js
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

Now open up `index.js` and add the new route.

```js
// ...
// import Repo
import Repo from './modules/Repo'

render((
  <Router history={hashHistory}>
    <Route path="/" component={App}>
      <Route path="/repos" component={Repos}/>
      {/* add the new route */}
      <Route path="/repos/:userName/:repoName" component={Repo}/>
      <Route path="/about" component={About}/>
    </Route>
  </Router>
), document.getElementById('app'))
```

Now we can add some links to this new route in `Repos.js`.

```js
// Repos.js
import { Link } from 'react-router'
// ...
export default React.createClass({
  render() {
    return (
      <div>
        <h2>Repos</h2>

        {/* add some links */}
        <ul>
          <li><Link to="/repos/reactjs/react-router">React Router</Link></li>
          <li><Link to="/repos/facebook/react">React</Link></li>
        </ul>

      </div>
    )
  }
})
```

Now go test your links out. Note that the parameter name in the route
`path` becomes the property name in the component. Both `repoName` and
`userName` are available on `this.props.params` of your component. You
should probably add some prop types to help others and yourself out
later.

---

[Next: More Nesting](../07-more-nesting/)