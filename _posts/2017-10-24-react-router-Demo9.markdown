---
layout: post
title:  "react router Demo9"
date:   2017-10-24 06:40:13 +0800
categories:  
tags: 
    - react
    - router

---  

source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/09-index-links)

### Note: ###



### Effect ###

![]()

### source code ###
powershell
```powershell
cd E:\n\learn\react\router\lessons\09-index-links
npm install
Start-Process chrome.exe http://localhost:8080/
npm start
```
index.js
```javascript 

```

index.css
```css 

```

index.html
```html  

```

modules/About.js
```javascript 

```

modules/App.js
```javascript 

```

modules/Home.js
```javascript 

```

modules/NavLink.js
```javascript 

```

modules/Repo.js
```javascript 

```

modules/Repos.js
```javascript 

```


## POST ##

# Index Links

Have you noticed in our app that we don't have any navigation to get
back to rendering the `Home` component?

Lets add a link to `/` and see what happens:

```js
// in App.js
// ...
<li><NavLink to="/">Home</NavLink></li>
// ...
```

Now navigate around. Notice anything weird? The link to `Home` is always
active! As we learned earlier, parent routes are active when child routes
are active. Unfortunately, `/` is the parent of everything.

For this link, we want it to only be active when the index route is
active. There are two ways to let the router know you're linking to the
"index route" so it only adds the active class (or styles) when the
index route is rendered.

## IndexLink

First let's use the `IndexLink` instead of `NavLink`

```js
// App.js
import { IndexLink } from 'react-router'

// ...
<li><IndexLink to="/" activeClassName="active">Home</IndexLink></li>
```

Fixed! Now this link is only "active" when we're at the index route. Go
ahead and click around to see.

## `onlyActiveOnIndex` Property

We can use `Link` as well by passing it the `onlyActiveOnIndex` prop
(`IndexLink` just wraps `Link` with this property for convenience).

```js
<li><Link to="/" activeClassName="active" onlyActiveOnIndex={true}>Home</Link></li>
```

That's fine, but we already abstracted away having to know what the
`activeClassName` is with `Nav`.

Remember, in `NavLink` we're passing along all of our props to `Link` with
the `{...spread}` syntax, so we can actually add the prop when we render
a `NavLink` and it will make its way down to the `Link`:

```js
<li><NavLink to="/" onlyActiveOnIndex={true}>Home</NavLink></li>
```

---

[Next: Clean URLs](../10-clean-urls/)