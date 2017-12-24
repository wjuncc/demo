---
layout: post
title:  "react router Demo10"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/10-clean-urls)

### Note: ###

What the different after STEP2? 


### Effect ###

![](https://i.imgur.com/nwbujOr.gif)

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\10-clean-urls
npm install
Start-Process chrome.exe http://localhost:8080/
npm start
```
index.js
```javascript 
import React from 'react'
import { render } from 'react-dom'
import { Router, Route, browserHistory, IndexRoute } from 'react-router'
import App from './modules/App'
import About from './modules/About'
import Repos from './modules/Repos'
import Repo from './modules/Repo'
import Home from './modules/Home'

render((
  <Router history={browserHistory}>
    <Route path="/" component={App}>
      <IndexRoute component={Home}/>
      <Route path="/repos" component={Repos}>
        <Route path="/repos/:userName/:repoName" component={Repo}/>
      </Route>
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
<link rel="stylesheet" href="/index.css">
<div id=app></div>
<script src="/bundle.js"></script>

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
          <li><NavLink to="/" onlyActiveOnIndex>Home</NavLink></li>
          <li><NavLink to="/about">About</NavLink></li>
          <li><NavLink to="/repos">Repos</NavLink></li>
        </ul>
        {this.props.children}
      </div>
    )
  }
})

```

modules/Home.js
```javascript 
import React from 'react'

export default React.createClass({
  render() {
    return <div>Home</div>
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
        {this.props.children}
      </div>
    )
  }
})

```


## POST ##

# Clean URLs with Browser History

The URLs in our app right now are built on a hack: the hash. It's the
default because it will always work, but there's a better way.

Modern browsers let JavaScript manipulate the URL without making an http
request, so we don't need to rely on the hash (`#`) portion of the url
to do routing, but there's a catch (we'll get to it later).

## Configuring Browser History

Open up `index.js` and import `browserHistory` instead of `hashHistory`.

```js
// index.js
// ...
// bring in `browserHistory` instead of `hashHistory`
import { Router, Route, browserHistory, IndexRoute } from 'react-router'

render((
  <Router history={browserHistory}>
    {/* ... */}
  </Router>
), document.getElementById('app'))
```

Now go click around and admire your clean URLs.

Oh yeah, the catch. Click on a link and then refresh your browser. What
happens?



![](https://i.imgur.com/ontr6ra.gif)
```
Cannot GET /repos
```
# STEP2 #
## Configuring Your Server

Your server needs to deliver your app no matter what URL comes in,
because your app, in the browser, is manipulating the URL. Our current
server doesn't know how to handle the URL.

The Webpack Dev Server has an option to enable this. Open up
`package.json` and add `--history-api-fallback`.

```json
    "start": "webpack-dev-server --inline --content-base . --history-api-fallback"
```

We also need to change our relative paths to absolute paths in
`index.html` since the URLs will be at deep paths and the app, if it
starts at a deep path, won't be able to find the files.

```html
<!-- index.html -->
<!-- index.css -> /index.css -->
<link rel="stylesheet" href="/index.css">

<!-- bundle.js -> /bundle.js -->
<script src="/bundle.js"></script>
```

Stop your server if it's running, then `npm start` again. Look at those
clean URLs :)

---

[Next: Production-ish Server](../11-productionish-server/)