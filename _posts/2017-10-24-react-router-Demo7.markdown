---
layout: post
title:  "react route Demo7"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/07-more-nesting)

### Note: ###



### Effect ###

![]()

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

```

index.html
```html  

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