---
layout: post
title:  "react route Demo1"
date:   2017-11-24 06:40:13 +0800
categories:  
tags: 
---

# react route 教程 #


source code from [git](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/01-setting-up)


## Effect ##

![](https://i.imgur.com/2szdmyi.png)

### source code ###

```powershell
cd E:\n\learn\react\router\react-router-tutorial-master\lessons\01-setting-up
npm install
npm start
```

```javascript
import React from 'react'

export default React.createClass({
  render() {
    return <div>Hello, React Router!</div>
  }
}) 
```


# Setting up the Project

First you'll need [Node.js](https://nodejs.org) and the package manager
that comes with it: [npm](https://www.npmjs.com/).

Once you've got that working, head to the command line where we'll set
up our project.

## Clone the Tutorial

```
git clone https://github.com/reactjs/react-router-tutorial
cd react-router-tutorial
cd lessons/01-setting-up
npm install
npm start
```

Now open up [http://localhost:8080](http://localhost:8080)

Feel free to poke around the code to see how we're using webpack and npm
scripts to run the app.

You should see a "Hello React Router" message in the browser.

## Make Some Changes

Open up `modules/App.js` and change the text to something like "Hello
<your name>". The browser automatically reloads with your new code.

---

[Next: Rendering a Router](../02-rendering-a-route/)



#### 参考 ####

* [React 技术栈系列教程 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2016/09/react-technology-stack.html)
* [React Router 使用教程 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2016/05/react_router.html)