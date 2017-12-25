---
layout: post
title:  "react route Demo2"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/02-rendering-a-route)

### Note: ###



### Effect ###

![](https://i.imgur.com/l2MtAwG.gif)

### source code ###

```powershell
cd E:\n\learn\react\router\lessons\02-rendering-a-route
npm install
Start-Process chrome.exe http://localhost:8080/
npm start
```

index.js
```javascript 
import React from 'react'
import { render } from 'react-dom'
import App from './modules/App'
import About from './modules/About'
import Repos from './modules/Repos'
import { Router, Route, hashHistory } from 'react-router'

render((
    <Router history={hashHistory}>
        <Route path="/" component={App}/>
        {/* add the routes here */}
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


## POST ##

# Rendering a Route

At its heart, React Router is a component.

```js
render(<Router/>, document.getElementById('app'))
```

That's not going to display anything until we configure a route.

Open up `index.js` and

1. import `Router`, `Route`, and `hashHistory`
2. render a `Router` instead of `App`

```js
// ...
import { Router, Route, hashHistory } from 'react-router'

render((
  <Router history={hashHistory}>
    <Route path="/" component={App}/>
  </Router>
), document.getElementById('app'))
```

Make sure your server is running with `npm start` and then visit
[http://localhost:8080](http://localhost:8080)

You should get the same screen as before, but this time with some junk
in the URL. We're using `hashHistory`--it manages the routing history
with the hash portion of the url. It's got that extra junk to shim some
behavior the browser has natively when using real urls.  We'll change
this to use real urls later and lose the junk, but for now, this works
great because it doesn't require any server-side configuration.


`junk in the URL` which means `http://localhost:8080/#/?_k=7o1yis`  in address bar likes:  
![](https://i.imgur.com/BB3O4SH.png)   
alse name `hashHistory`.

notice:`it doesn't require any server-side configuration.`


## Adding More Screens

Create two new components at:

- `modules/About.js`
- `modules/Repos.js`

```js
// modules/About.js
import React from 'react'

export default React.createClass({
  render() {
    return <div>About</div>
  }
})
```

```js
// modules/Repos.js
import React from 'react'

export default React.createClass({
  render() {
    return <div>Repos</div>
  }
})
```

Now we can couple them to the app at their respective paths.

```js
// insert into index.js
import About from './modules/About'
import Repos from './modules/Repos'

render((
  <Router history={hashHistory}>
    <Route path="/" component={App}/>
    {/* add the routes here */}
    <Route path="/repos" component={Repos}/>
    <Route path="/about" component={About}/>
  </Router>
), document.getElementById('app'))
```

Now visit [http://localhost:8080/#/about](http://localhost:8080/#/about) and
[http://localhost:8080/#/repos](http://localhost:8080/#/repos)

---

[Next: Navigating With Link](../03-navigating-with-link/)