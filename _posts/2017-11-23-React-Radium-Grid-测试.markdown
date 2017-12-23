---
layout: post
title:  "React Radium Grid 测试"
date:   2017-11-23 00:00:58 +0800
categories:  
tags: 
    - react 

---

#  A Simple Demo Of React Radium Grid #

This one is neither suitable in mini-site nor correct in back-end interface in producing enviroment, for the mini-site's css exports from the psd , and then modify to css-module in react.On the other hand, ui suite like Meteor and react-ui is a better choose for back-end ui, without the incompatible problem caused by various ui-components. 

example code form [Radium Grid: A React Grid System Injected With The Power Of Radium](http://formidable.com/blog/2016/06/20/radium-grid-a-react-grid-system-injected-with-the-power-of-radium/?utm_content=buffercba8a&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)

* Radium Grid: 
* [git](https://github.com/FormidableLabs/radium-grid)

to install radium-grid, running script:
```powershell
cd path-of-directory
npm install --save radium-grid
```
effect:  
![1](https://i.imgur.com/uLot9qU.gif)

source code:

```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
import { Grid, Cell } from 'radium-grid';

const { StyleRoot } = Radium;

const styles = {
    cell: {
        boxSizing: "border-box",
        color: "#fff",
        fontFamily: "'微软雅黑','Helvetica Neue', Helvetica, Verdana, sans-serif",
        background: "#ff4136",
        marginBottom: "1rem",
        padding: "1rem",
        minWidth: "0px",
        height: "150px"
    }
}

const Demo = () => {
    return (
        <StyleRoot>
            <Grid>
                <Cell style={[styles.cell]}>
                    <p>1个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>2个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>3个产品</p>
                </Cell>
            </Grid>
        </StyleRoot>
    );
};

render(<Demo />, document.querySelector('#container'));
```
The above example will render with the following provided defaults:

* All cells in the grid are 1/3 wide for all screen sizes.
* The grid uses a 16px fixed gutter.
* Cell content is aligned to the top left.
* The breakpoints use the following media queries:
	* small: "@media only screen and (max-width: 640px)",
	* medium: "@media only screen and (min-width: 641px) and (max-width: 1024px)",
	* large: "@media only screen and (min-width: 1025px) and (max-width: 1440px)",
	* xlarge: "@media only screen and (min-width: 1441px)"

local directory:

cd E:\n\learn\react\css\demo4


gif:  
![2](https://i.imgur.com/e9bGdK4.gif)

source code:
```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
import { Grid, Cell } from 'radium-grid';

const { StyleRoot } = Radium;

const styles = {
    cell: {
        boxSizing: "border-box",
        color: "#fff",
        fontFamily: "'微软雅黑','Helvetica Neue', Helvetica, Verdana, sans-serif",
        background: "#ff4136",
        marginBottom: "1rem",
        padding: "1rem",
        minWidth: "0px",
        height: "150px"
    }
}

const Demo = () => {
    return (
        <StyleRoot>
            <Grid cellWidth="1/2">
                <Cell style={[styles.cell]}>
                    <p>1个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>2个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>3个产品</p>
                </Cell>
            </Grid>
        </StyleRoot>
    );
};

render(<Demo />, document.querySelector('#container'));
```


An example of setting widths and alignment per screen size for every cell in the grid:

local directory:

cd E:\n\learn\react\css\demo5


gif:  
![2](https://i.imgur.com/xHROrXp.gif)

source code:
```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
import { Grid, Cell } from 'radium-grid';

const { StyleRoot } = Radium;

const styles = {
    cell: {
        boxSizing: "border-box",
        color: "#fff",
        fontFamily: "'微软雅黑','Helvetica Neue', Helvetica, Verdana, sans-serif",
        background: "#ff4136",
        marginBottom: "1rem",
        padding: "1rem",
        minWidth: "0px",
        height: "150px"
    }
}

const Demo = () => {
    return (
        <StyleRoot>
            <Grid
                smallCellWidth="1"
                smallAlign="right"
                smallVerticalAlign="bottom"
                mediumCellWidth="1"
                mediumCellAlign="right"
                mediumCellVerticalAlign="bottom"
            >
                <Cell style={[styles.cell]}>
                    <p>1个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>2个产品</p>
                </Cell>
                <Cell style={[styles.cell]}>
                    <p>3个产品</p>
                </Cell>
            </Grid>
        </StyleRoot>
    );
};

render(<Demo />, document.querySelector('#container'));
```





local directory:

cd E:\n\learn\react\css\demo6


gif:  
![2](https://i.imgur.com/xGhvKfC.gif)

source code:
```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
import { Grid, Cell } from 'radium-grid';

const { StyleRoot } = Radium;

const styles = {
    cell: {
        boxSizing: "border-box",
        color: "#fff",
        fontFamily: "'微软雅黑','Helvetica Neue', Helvetica, Verdana, sans-serif",
        background: "#ff4136",
        marginBottom: "1rem",
        padding: "1rem",
        minWidth: "0px",
        height: "150px"
    }
}

const Demo = () => {
    return (
        <StyleRoot>
            <Grid>
                <Cell
                    style={[styles.cell]}
                    align="right"
                    verticalAlign="bottom"
                    width="1/4"
                >
                    <p>1个产品</p>
                </Cell>
                <Cell
                    style={[styles.cell]}
                    align="left"
                    verticalAlign="top"
                    width="3/4"
                >
                    <p>2个产品</p>
                </Cell>
                <Cell
                    style={[styles.cell]}
                    align="right"
                    verticalAlign="bottom"
                    width="3/4"
                >
                    <p>3个产品</p>
                </Cell>
                <Cell
                    style={[styles.cell]}
                    align="left"
                    verticalAlign="top"
                    width="1/4"
                >
                    <p>4个产品</p>
                </Cell>
            </Grid>
        </StyleRoot>
    );
};

render(<Demo />, document.querySelector('#container'));
```

The same as above, but with different per-cell widths on small screens:


local directory:

cd E:\n\learn\react\css\demo7


gif:  
![2](https://i.imgur.com/9MGEOyk.gif)

source code:
```javascript
import React from 'react';
import { render } from 'react-dom';
import Radium from 'radium';
import { Grid, Cell } from 'radium-grid';

const { StyleRoot } = Radium;

const styles = {
    cell: {
        boxSizing: "border-box",
        color: "#fff",
        fontFamily: "'微软雅黑','Helvetica Neue', Helvetica, Verdana, sans-serif",
        background: "#ff4136",
        marginBottom: "1rem",
        padding: "1rem",
        minWidth: "0px",
        height: "150px"
    }
}

const Demo = () => {
    return (
        <StyleRoot>
            <Grid>
                <Cell
                    style={[styles.cell]}
                    align="right"
                    verticalAlign="bottom"
                    width="1/4"
                    smallWidth="1/2"
                >
                    <p>1个产品</p>
                </Cell>
                <Cell
                    style={[styles.cell]}
                    align="left"
                    verticalAlign="top"
                    width="3/4"
                    smallWidth="1/2"
                >
                    <p>2个产品</p>
                </Cell>
            </Grid>
        </StyleRoot>
    );
};

render(<Demo />, document.querySelector('#container'));
```




local directory:

cd E:\n\learn\react\css\demo8


gif:  
![2](https://i.imgur.com/e9bGdK4.gif)

source code:
```javascript

```

