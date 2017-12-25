---
layout: post
title:  "React Redux 入门教程1 基本用法"
date:   2017-10-03 11:21:56 +0800
categories:  
tags: 
    - react

---

toturial from [Redux 入门教程（一）：基本用法 - 阮一峰](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)
 

# Redux 入门教程（一）：基本用法

React没涉及。 

- 代码结构
- 组件之间的通信 

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016091801.png)

## 零、你可能不需要 Redux

> "如果你不知道是否需要 Redux，那就是不需要它。"

> "只有遇到 React 实在解决不了的问题，你才需要 Redux 。"

简单说，如果你的UI层非常简单，没有很多互动，Redux 就是不必要的，用了反而增加复杂性。

> - 用户的使用方式非常简单
> - 用户之间没有协作
> - 不需要与服务器大量交互，也没有使用 WebSocket
> - 视图层（View）只从单一来源获取数据

上面这些情况，都不需要使用 Redux。

> - 用户的使用方式复杂
> - 不同身份的用户有不同的使用方式（比如普通用户和管理员）
> - 多个用户之间可以协作
> - 与服务器大量交互，或者使用了WebSocket
> - View要从多个来源获取数据

上面这些情况才是 Redux 的适用场景：多交互、多数据源。

从组件角度看，如果你的应用有以下场景，可以考虑使用 Redux。

> - 某个组件的状态，需要共享
> - 某个状态需要在任何地方都可以拿到
> - 一个组件需要改变全局状态
> - 一个组件需要改变另一个组件的状态

发生上面情况时，如果不使用 Redux 或者其他状态管理工具，不按照一定规律处理状态的读写，代码很快就会变成一团乱麻。你需要一种机制，可以在同一个地方查询状态、改变状态、传播状态的变化。

## 一、预备知识 

Redux [文档](http://redux.js.org/)，配套视频（[前30集](https://egghead.io/courses/getting-started-with-redux)，[后30集](https://egghead.io/courses/building-react-applications-with-idiomatic-redux)）。你可以先阅读本文，再去官方材料详细研究。 

## 二、设计思想

Redux 的设计思想很简单，就两句话。

> （1）Web 应用是一个状态机，视图与状态是一一对应的。
> 
> （2）所有的状态，保存在一个对象里面。

## 三、基本概念和 API

### 3.1 Store

Store 就是保存数据的地方，你可以把它看成一个容器。整个应用只能有一个 Store。

Redux 提供`createStore`这个函数，用来生成 Store。

>     
>     import { createStore } from 'redux';
>     const store =createStore(fn);

上面代码中，`createStore`函数接受另一个函数作为参数，返回新生成的 Store 对象。

### 3.2 State

`Store`对象包含所有数据。如果想得到某个时点的数据，就要对 Store 生成快照。这种时点的数据集合，就叫做 State。

当前时刻的 State，可以通过`store.getState()`拿到。

>     
>     import { createStore } from 'redux';
>     const store =createStore(fn);
>     
>     const state = store.getState();

Redux 规定， 一个 State 对应一个 View。只要 State 相同，View 就相同。你知道 State，就知道 View 是什么样，反之亦然。

### 3.3 Action

State 的变化，会导致 View 的变化。但是，用户接触不到 State，只能接触到 View。所以，State 的变化必须是 View 导致的。Action 就是 View 发出的通知，表示 State 应该要发生变化了。

Action 是一个对象。其中的`type`属性是必须的，表示 Action 的名称。其他属性可以自由设置，社区有一个[规范](https://github.com/acdlite/flux-standard-action)可以参考。

>     
>     const action ={
>       type:'ADD_TODO',
>       payload:'Learn Redux'};

上面代码中，Action 的名称是`ADD_TODO`，它携带的信息是字符串`Learn Redux`。

可以这样理解，Action 描述当前发生的事情。改变 State 的唯一办法，就是使用 Action。它会运送数据到 Store。

### 3.4 Action Creator

View 要发送多少种消息，就会有多少种 Action。如果都手写，会很麻烦。可以定义一个函数来生成 Action，这个函数就叫 Action Creator。

>     
>     const ADD_TODO ='添加 TODO';functionaddTodo(text){return{
>         type: ADD_TODO,
>         text
>       }}
>     
>     const action =addTodo('Learn Redux');

上面代码中，`addTodo`函数就是一个 Action Creator。

### 3.5 store.dispatch()

`store.dispatch()`是 View 发出 Action 的唯一方法。

>     
>     import { createStore } from 'redux';
>     const store =createStore(fn);
>     
>     store.dispatch({
>       type:'ADD_TODO',
>       payload:'Learn Redux'});

上面代码中，`store.dispatch`接受一个 Action 对象作为参数，将它发送出去。

结合 Action Creator，这段代码可以改写如下。

>     
>     store.dispatch(addTodo('Learn Redux'));

## 3.6 Reducer

Store 收到 Action 以后，必须给出一个新的 State，这样 View 才会发生变化。这种 State 的计算过程就叫做 Reducer。

Reducer 是一个函数，它接受 Action 和当前 State 作为参数，返回一个新的 State。

>     
>     const reducer =function(state, action){ // ...
>     return new_state;};

整个应用的初始状态，可以作为 State 的默认值。下面是一个实际的例子。

>     
>     const defaultState =0;
>     const reducer =(state = defaultState, action)=>{
>       switch (action.type){
>         case 'ADD':return state + action.payload;
>         default:return state;}};
>     
>     const state =reducer(1,{
>       type:'ADD',
>       payload:2});

上面代码中，`reducer`函数收到名为`ADD`的 Action 以后，就返回一个新的 State，作为加法的计算结果。其他运算的逻辑（比如减法），也可以根据 Action 的不同来实现。

实际应用中，Reducer 函数不用像上面这样手动调用，`store.dispatch`方法会触发 Reducer 的自动执行。为此，Store 需要知道 Reducer 函数，做法就是在生成 Store 的时候，将 Reducer 传入`createStore`方法。

>     
>     import { createStore } from 'redux';
>     const store =createStore(reducer);

上面代码中，`createStore`接受 Reducer 作为参数，生成一个新的 Store。以后每当`store.dispatch`发送过来一个新的 Action，就会自动调用 Reducer，得到新的 State。

为什么这个函数叫做 Reducer 呢？因为它可以作为数组的`reduce`方法的参数。请看下面的例子，一系列 Action 对象按照顺序作为一个数组。

>     
>     const actions =[{ type:'ADD', payload:0},{ type:'ADD', payload:1},{ type:'ADD', payload:2}];
>     
>     const total = actions.reduce(reducer,0); // 3
>     

上面代码中，数组`actions`表示依次有三个 Action，分别是加`0`、加`1`和加`2`。数组的`reduce`方法接受 Reducer 函数作为参数，就可以直接得到最终的状态`3`。

### 3.7 纯函数

Reducer 函数最重要的特征是，它是一个纯函数。也就是说，只要是同样的输入，必定得到同样的输出。

纯函数是函数式编程的概念，必须遵守以下一些约束。

> - 不得改写参数
> - 不能调用系统 I/O 的API
> - 不能调用`Date.now()`或者`Math.random()`等不纯的方法，因为每次会得到不一样的结果

由于 Reducer 是纯函数，就可以保证同样的State，必定得到同样的 View。但也正因为这一点，Reducer 函数里面不能改变 State，必须返回一个全新的对象，请参考下面的写法。

>     
>     // State 是一个对象
>     functionreducer(state, action){return Object.assign({}, state,{ thingToChange }); // 或者
>     return{...state,...newState };}
>     // State 是一个数组
>     functionreducer(state, action){return[...state, newItem];}

最好把 State 对象设成只读。你没法改变它，要得到新的 State，唯一办法就是生成一个新对象。这样的好处是，任何时候，与某个 View 对应的 State 总是一个不变的对象。

### 3.8 store.subscribe()

Store 允许使用`store.subscribe`方法设置监听函数，一旦 State 发生变化，就自动执行这个函数。

>     
>     import { createStore } from 'redux';
>     const store =createStore(reducer);
>     
>     store.subscribe(listener);

显然，只要把 View 的更新函数（对于 React 项目，就是组件的`render`方法或`setState`方法）放入`listen`，就会实现 View 的自动渲染。

`store.subscribe`方法返回一个函数，调用这个函数就可以解除监听。

>     let unsubscribe = store.subscribe(()=>
>       console.log(store.getState()));unsubscribe();

## 四、Store 的实现

上一节介绍了 Redux 涉及的基本概念，可以发现 Store 提供了三个方法。

> - store.getState()
> - store.dispatch()
> - store.subscribe()

>     
>     import { createStore } from 'redux';let{ subscribe, dispatch, getState }=createStore(reducer);

`createStore`方法还可以接受第二个参数，表示 State 的最初状态。这通常是服务器给出的。

>     let store =createStore(todoApp, window.STATE_FROM_SERVER)

上面代码中，`window.STATE_FROM_SERVER`就是整个应用的状态初始值。注意，如果提供了这个参数，它会覆盖 Reducer 函数的默认初始值。

下面是`createStore`方法的一个简单实现，可以了解一下 Store 是怎么生成的。

>     
>     const createStore =(reducer)=>{let state;let listeners =[];
>     
>       const getState =()=> state;
>     
>       const dispatch =(action)=>{
>         state =reducer(state, action);
>         listeners.forEach(listener =>listener());};
>     
>       const subscribe =(listener)=>{
>         listeners.push(listener);return()=>{
>           listeners = listeners.filter(l => l !== listener);}};dispatch({});return{ getState, dispatch, subscribe };};

## 五、Reducer 的拆分

Reducer 函数负责生成 State。由于整个应用只有一个 State 对象，包含所有数据，对于大型应用来说，这个 State 必然十分庞大，导致 Reducer 函数也十分庞大。

请看下面的例子。

>     
>     const chatReducer =(state = defaultState, action ={})=>{
>       const { type, payload }= action;
>       switch (type){
>         case ADD_CHAT:return Object.assign({}, state,{
>             chatLog: state.chatLog.concat(payload)});
>         case CHANGE_STATUS:return Object.assign({}, state,{
>             statusMessage: payload
>           });
>         case CHANGE_USERNAME:return Object.assign({}, state,{
>             userName: payload
>           });
>         default:return state;}};

上面代码中，三种 Action 分别改变 State 的三个属性。

> - ADD_CHAT：`chatLog`属性
> - CHANGE_STATUS：`statusMessage`属性
> - CHANGE_USERNAME：`userName`属性

这三个属性之间没有联系，这提示我们可以把 Reducer 函数拆分。不同的函数负责处理不同属性，最终把它们合并成一个大的 Reducer 即可。

>     
>     const chatReducer =(state = defaultState, action ={})=>{return{
>         chatLog:chatLog(state.chatLog, action),
>         statusMessage:statusMessage(state.statusMessage, action),
>         userName:userName(state.userName, action)}};

上面代码中，Reducer 函数被拆成了三个小函数，每一个负责生成对应的属性。

这样一拆，Reducer 就易读易写多了。而且，这种拆分与 React 应用的结构相吻合：一个 React 根组件由很多子组件构成。这就是说，子组件与子 Reducer 完全可以对应。

Redux 提供了一个`combineReducers`方法，用于 Reducer 的拆分。你只要定义各个子 Reducer 函数，然后用这个方法，将它们合成一个大的 Reducer。

>     
>     import { combineReducers } from 'redux';
>     
>     const chatReducer =combineReducers({
>       chatLog,
>       statusMessage,
>       userName
>     })
>     
>     export default todoApp;

上面的代码通过`combineReducers`方法将三个子 Reducer 合并成一个大的函数。

这种写法有一个前提，就是 State 的属性名必须与子 Reducer 同名。如果不同名，就要采用下面的写法。

>     
>     const reducer =combineReducers({
>       a: doSomethingWithA,
>       b: processB,
>       c: c
>     })
>     // 等同于
>     functionreducer(state ={}, action){return{
>         a:doSomethingWithA(state.a, action),
>         b:processB(state.b, action),
>         c:c(state.c, action)}}

总之，`combineReducers()`做的就是产生一个整体的 Reducer 函数。该函数根据 State 的 key 去执行相应的子 Reducer，并将返回结果合并成一个大的 State 对象。

下面是`combineReducer`的简单实现。

>     
>     const combineReducers = reducers =>{return(state ={}, action)=>{return Object.keys(reducers).reduce((nextState, key)=>{
>             nextState[key]= reducers[key](state[key], action);return nextState;},{});};};

你可以把所有子 Reducer 放在一个文件里面，然后统一引入。

>     
>     import { combineReducers } from 'redux'
>     import * as reducers from './reducers'
>     
>     const reducer =combineReducers(reducers)

## 六、工作流程

本节对 Redux 的工作流程，做一个梳理。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016091802.jpg)

首先，用户发出 Action。

>     
>     store.dispatch(action);

然后，Store 自动调用 Reducer，并且传入两个参数：当前 State 和收到的 Action。 Reducer 会返回新的 State 。

>     let nextState =todoApp(previousState, action);

State 一旦有变化，Store 就会调用监听函数。

>     
>     // 设置监听函数
>     store.subscribe(listener);

`listener`可以通过`store.getState()`得到当前状态。如果使用的是 React，这时可以触发重新渲染 View。

>     functionlisterner(){let newState = store.getState();
>       component.setState(newState);}

## 七、实例：计数器

下面我们来看一个最简单的实例。

>     
>     const Counter =({ value })=>(<h1>{value}</h1>);
>     
>     const render =()=>{
>       ReactDOM.render(<Counter value={store.getState()}/>,
>         document.getElementById('root'));};
>     
>     store.subscribe(render);render();

上面是一个简单的计数器，唯一的作用就是把参数`value`的值，显示在网页上。Store 的监听函数设置为`render`，每次 State 的变化都会导致网页重新渲染。

下面加入一点变化，为`Counter`添加递增和递减的 Action。

>     
>     const Counter =({ value, onIncrement, onDecrement })=>(<div><h1>{value}</h1><button onClick={onIncrement}>+</button><button onClick={onDecrement}>-</button></div>);
>     
>     const reducer =(state =0, action)=>{
>       switch (action.type){
>         case 'INCREMENT':return state +1;
>         case 'DECREMENT':return state -1;
>         default:return state;}};
>     
>     const store =createStore(reducer);
>     
>     const render =()=>{
>       ReactDOM.render(<Counter
>           value={store.getState()}
>           onIncrement={()=> store.dispatch({type:'INCREMENT'})}
>           onDecrement={()=> store.dispatch({type:'DECREMENT'})}/>,
>         document.getElementById('root'));};render();
>     store.subscribe(render);

完整的代码请看[这里](https://github.com/reactjs/redux/tree/master/examples/counter)。

Redux 的基本用法就介绍到这里，[下一次](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)介绍它的高级用法：中间件和异步操作。

（完）

## 相关文章

- **2017.09.19: [《ES6 标准入门（第3版）》上市了！](http://www.ruanyifeng.com/blog/2017/09/es6_primer_3rd_edition.html)**

                              2017年6月，TC39 委员会正式发布了《ES2017 标准》。

                           

- **2017.09.07: [asm.js 和 Emscripten 入门教程](http://www.ruanyifeng.com/blog/2017/09/asmjs_emscripten.html)**

                              Web 技术突飞猛进，但是有一个领域一直无法突破 ---- 游戏。

                           

- **2017.08.09: [Koa 框架教程](http://www.ruanyifeng.com/blog/2017/08/koa.html)**

                              Node 主要用在开发 Web 应用。这决定了使用 Node，往往离不开 Web 应用框架。

                           

- **2017.04.16: [JavaScript 内存泄漏教程](http://www.ruanyifeng.com/blog/2017/04/memory-leak.html)**

                              一、什么是内存泄漏？

程序的运行需要内存。只要程序提出要求，操作系统或者运行时（runtime）就必须供给内存。

                           

## 广告[（购买广告位）](/support.html)

[![妙味课堂](http://www.ruanyifeng.com/blog/images/sup_miaov_201711.jpg)](http://www.miaov.com/index.php/example/exampleList?utm_source=ruanyifeng&amp;)

[![腾讯课堂](http://www.ruanyifeng.com/blog/images/sup_qqke_20171202.png)](https://ke.qq.com/next/index.html?from=175763)

## 留言（96条）
                

redux这一块难咬的骨头，期待阮老师的redux解读，占楼。


Redux 的工作流程图中指向Action Creators的箭头画偏了


一直都看阮老师的博客，写得太好了。通俗易懂，简单明了，需要强大的功底。期待老师的续讲！

                

个人觉得redux唯一的好处就是增加了一点代码的可维护性， 依靠强制reducer保持简单， component仅仅处理一些UI logic,  使用provider 和 connect来向component中注入state, 但这些并不会减少代码量， 而且作者特意强调的container component和presentation component， 这种区分当然是好的， 但并没有带来复用的好处，就像作者自己做的TODOMVC，里面无论是哪个component都没有复用性可言，是真正的demo oriented programming

2016年9月18日 21:50
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364717)
 | [引用](#comment-text)

what happen

 说：
                

希望后面几期能捎带手讲讲 redux-saga 

2016年9月18日 22:04
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364718)
 | [引用](#comment-text)

fusun

 说：
                

reducer拆封没看懂
                

不错，我昨天还在想，你什么时候出这个rudux的东西。

                

這部分還是推薦看Dan的視頻，跟他走一遍TodoList的流程，就會了解Redux解決了哪些問題。 

redux本身很简单，麻烦的是后面用到的异步action,然后各种插件，特别是需要结合react时，redux-thunk,redux-form,react-router-redux各种插件结合用。

拿个项目练练手就好，关键在于state结构的设计，不然项目膨胀后，自己都不知道去哪找需要的值。

工具redux devtools必备。

然后就是各种辅助了，webpack打包，测试。

继续关注博主的这个系列


>     引用fusun的发言：
> 
> 
> reducer拆封没看懂

其实这玩意就是一个强制约束，reducer 用一行代码解释就是

>      (state, action) => state
>     

返回一个新的state, 将原有的值覆盖，记住3大原则就好。然后习惯了，就会觉得很妙了。

2016年9月20日 09:31
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364765)
 | [引用](#comment-text)

[geeksuen](http://geeksuen.github.io)

 说：
                

Reducer 函数拆分这里

const chatReducer = (state = defaultState, action = {}) => {

  return {

    chatLog: chatLog(state.chatLog, action),

    statusMessage: statusMessage(state.statusMessage, action),

    userName: userName(state.userName, action)

  }

};

原来是根据action.type进行判断，到了这里就看不懂了，求详解

2016年9月20日 09:40
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364766)
 | [引用](#comment-text)

刀尖

 说：
                

最后那个计数，实在不能苟同，这么写，React就不是React了，忽略了React状态机的本质

2016年9月20日 18:45
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364851)
 | [引用](#comment-text)

atom

 说：
                

有一个 Redux 莞式教程 [https://github.com/kenberkeley/redux-simple-tutorial，貌似跟博主的行文差不多。。。](https://github.com/kenberkeley/redux-simple-tutorial，貌似跟博主的行文差不多。。。)

2016年9月20日 22:06
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364855)
 | [引用](#comment-text)

kanglin

 说：
                

const chatReducer = (state = defaultState, action = {}) => {

  return {

    chatLog: chatLog(state.chatLog, action),

    statusMessage: statusMessage(state.statusMessage, action),

    userName: userName(state.userName, action)

  }

};

//为什么这里返回的一个对象？怎生产生新的state呢？

2016年9月21日 02:30
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364859)
 | [引用](#comment-text)

[令狐葱](http://jiji262.github.io/)

 说：
                

在Redux之前，是否应该对flux做个介绍？

求《flux入门教程》。

2016年9月21日 16:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364902)
 | [引用](#comment-text)

yy

 说：
                

3.4里面的对象好像落了key


@yy：这是ES6的语法，请看下面的链接

[http://es6.ruanyifeng.com/#docs/object#属性的简洁表示法](http://es6.ruanyifeng.com/#docs/object#属性的简洁表示法)

2016年9月21日 21:04
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364909)
 | [引用](#comment-text)

leeds

 说：
                

请教，使用了websocket，为什么就需要用redux了，搜索了下没找到相关文章

给个推荐看的链接也行

                

虽然用redux已经有一段时间了，但是只能说会用，没有捋清楚底层的用意，老师的讲解从更高的层次进行了讲解，有种豁然开朗的感觉，感谢

2016年9月22日 14:20
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364925)
 | [引用](#comment-text)

软刀

 说：
                

>     引用geeksuen的发言：
> 
> 
> Reducer 函数拆分这里
> 
> const chatReducer = (state = defaultState, action = {}) => {
> 
> return {
> 
> chatLog: chatLog(state.chatLog, action),
> 
> statusMessage: statusMessage(state.statusMessage, action),
> 
> userName: userName(state.userName, action)
> 
> }
> 
> };
> 
> 原来是根据action.type进行判断，到了这里就看不懂了，求详解

我也没看懂。。。

2016年9月23日 09:16
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-364980)
 | [引用](#comment-text)

Slowly

 说：
                

有没有react-redux的大神 妹子我有问题想请教 thank u

2016年9月23日 14:29
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365055)
 | [引用](#comment-text)

superwf

 说：
                

中等规模的项目就可以用，刚用react的时候的第一个项目没用，后来就发现数据与ui层的状态互相交织挺乱的

第二个项目用redux很好的分离了，不过确实是需要多写两层action，和reducer，好在增加了这两个货之后测试真的变得方便了很多，以前好多很难测的场景都被redux分离了出来．

2016年9月23日 16:54
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365062)
 | [引用](#comment-text)

l1xnan

 说：
                

看到 React-Router 后一直期待 React-Redux 系列。。。

2016年9月23日 20:24
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365070)
 | [引用](#comment-text)

wv1124

 说：
                

感觉iFlex2要比redux好用
[https://github.com/QianmiOpen/iflux2](https://github.com/QianmiOpen/iflux2)

2016年9月23日 21:23
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365073)
 | [引用](#comment-text)

[jaychang](http://jaychang@iteye.com)

 说：
                

有个问题 State 对象设成只读，这个该如何设置？

2016年9月24日 15:09
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365109)
 | [引用](#comment-text)

[jaychang](http://jaychang@iteye.com)

 说：
                

store.subscribe(listener);

显然，只要把 View 的更新函数（对于 React 项目，就是组件的render方法或setState方法）放入listen，就会实现 View 的自动渲染。

listener是组件的render方法好理解，但是setState方法作为listener，表示很费解，不是说store的state是映射到组件的props上的么?不是跟组件的state没关系么? 

求解

2016年9月24日 15:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365110)
 | [引用](#comment-text)

[jaychang](http://jaychang@iteye.com)

 说：
                

关于createStore中subscribe的实现：

没理解为什么最后要返回

 return () => {

      listeners = listeners.filter(l => l !== listener);

 }

感觉没什么用

2016年9月24日 16:57
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365118)
 | [引用](#comment-text)

[jaychang](http://jaychang@iteye.com)

 说：
                

@geeksuen：

const combineReducers = reducers => {

  return (state = {}, action) => {

    return Object.keys(reducers).reduce(

      (nextState, key) => {

        nextState[key] = reducers[key](state[key], action);

        return nextState;

      },

      {} 

    );

  };

};

还是根据action.type进行判断的，当store.dispatch(action)时，会执行所有的reducer,如果action.type在reducer里面做switch操作的时候匹配不到，是不会改变state的。

比如你combineReducers({key1:reducer1,key2:reducer2})，当store.dispatch(action)时，reducer1,reducer2都会执行。

关键时看combineReducers执行完后，得到的合并的reducer函数

关键在这里reducerKeys.reduce(function(nextState,reducerKey){...},{})理解了这一段，就会觉得豁然开朗。

2016年9月24日 21:34
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365119)
 | [引用](#comment-text)

[avilang](http://avilang.me)

 说：
                

再次感谢阮老师，分享那么好的文章~~

2016年10月 7日 10:47
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-365805)
 | [引用](#comment-text)

[echoloyuk](http://www.himachi.cn)

 说：
                

>     引用刀尖的发言：
> 
> 
> 最后那个计数，实在不能苟同，这么写，React就不是React了，忽略了React状态机的本质

我也感觉是，计数的demo感觉靠的是刷新整个Component，忽略了React本身的状态机制。这和用jQuery重新刷新整个页面本质上没什么区别。

2016年10月12日 12:22
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366228)
 | [引用](#comment-text)

赵春森

 说：
                

3.6 Reducer

const actions = [

  { type: 'ADD', payload: 0 },

  { type: 'ADD', payload: 1 },

  { type: 'ADD', payload: 2 }

];

const total = actions.reduce(reducer, 0); // 3

前几天自己看资料写了一个demo.其他的都能理解,这一块实在没看懂. 有人懂的人把代码补全么？

2016年10月14日 13:29
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366355)
 | [引用](#comment-text)

赵春森

 说：
                

@赵春森：

已经找到了,和redux无关. 自己知识量不够.  参考

[https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

2016年10月14日 15:23
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366362)
 | [引用](#comment-text)

刘迪

 说：
                

阮老师：请问react如何解决移动端click事件300ms左右延迟的问题

2016年10月19日 20:48
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366679)
 | [引用](#comment-text)

[Victoria](http://weibo.com/3918265068/profile?rightmod=1&amp;wvr=6&amp;mod=personinfo&amp;is_all=1)

 说：
                

大神，我微博居然一直在关注你，刚刚看到你的个人网站，教程很有用~~~

2016年10月20日 14:05
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366744)
 | [引用](#comment-text)

Jashon

 说：
                

>     引用kanglin的发言：
> 
> 
> const chatReducer = (state = defaultState, action = {}) => {
> 
> return {
> 
> chatLog: chatLog(state.chatLog, action),
> 
> statusMessage: statusMessage(state.statusMessage, action),
> 
> userName: userName(state.userName, action)
> 
> }
> 
> };
> 
> //为什么这里返回的一个对象？怎生产生新的state呢？

返回的是一整个state对象，然后根据需要取state对象里面的具体属性
        

2016年10月21日 14:09
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-366796)
 | [引用](#comment-text)

M

 说：
                

MultCloud(https://www.multcloud.com/), a FREE and easy-to-use web app, supports for Managing Files and Transferring Files across Cloud Drives. Free provide 10TB traffic for data transmission.

2016年11月 1日 14:27
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-367507)
 | [引用](#comment-text)

Grubby

 说：
                

>     引用jaychang的发言：
> 
> 
> 关于createStore中subscribe的实现：
> 
> 没理解为什么最后要返回
> 
>  return () => {
> 
> listeners = listeners.filter(l => l !== listener);
> 
>  }
> 
> 感觉没什么用

这个很简单，直接使用subscribe会把你要监听的事件添加到数组，但是这个方法本身返回值是也是一个方法（简称unSubscribe方法），执行这个unSubscribe会移除监听事件，所以作者在写这个方法时候通过filter过滤，执行的时候将之前本身已经添加进数组的事件名移除数组。

        
   

其实就是Erlang的思想
  

很好的文章，这些目前都用上了

                

用上了，谢谢！看一遍就有很好的了解！教程行云流水！

Redux 的设计思想很简单，就两句话。

（1）Web 应用是一个状态机，视图与状态是一一对应的。

（2）所有的状态，保存在一个对象里面。

这里面的“所有的状态，保存在一个对象里面。”，也包括components 的state吗？

                

const Counter = ({ value }) => (

  {value}

  +

  -

);

阮老师，这个地方没有看懂 

1.value通过解构赋值，但是onIncrement和onDecrement怎么取到值？

2.三个元素不是要放在一个div里面吗
       

state不是应该对应每个view吗？全局只有一个store，但是可以有多个state吗？您在第五部分说全局只有一个state？

                

ha,看了阮老师的教程，终于把redux搞懂了
        

最后一个例子，Counter组件中，传入的参数不应该是{value} ,应该是{value,onIncrement,onDecrement}吧，不然，经实测，函数总报错onIncrement和onDecrement未定义。

还有一个问题，这里之所以传入一个对象，是理解为对象的解构赋值吗，这个对象与Counter组件的属性对象相对应？

 说：
                

我刚才留言成功了怎么没有显示？再来一发。

@软刀

combineReducers 没看懂的同学看这里，官网文档：
[https://github.com/reactjs/redux/blob/master/docs/api/combineReducers.md](https://github.com/reactjs/redux/blob/master/docs/api/combineReducers.md)

const rootReducer = combineReducers({

    numReducer, //相当于一个同名的 key：value, 通过 store.getState().numReducer 获取对应的state

});

这样是不是懂了呢~~

2017年1月 6日 15:55
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-371663)
 | [引用](#comment-text)

Andy

 说：
                

疑问：

1. 调用 store.dispatch(action) 的时候，每个reducer都会收到然后在switch，会不会有性能问题？能不能直接发给对应的reducer?

2.获取数据的时候store.getState()是获取全部数据, 虽然可以store.getState().xxxRender 获取对应render的state, 但每次都要获取所有数据会不会有性能问题？

2017年1月 6日 16:38
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-371668)
 | [引用](#comment-text)

zhóu

 说：
                

function listerner() {

  let newState = store.getState();

  component.setState(newState);   

}

为什么需要手动修改state了 ， state不是已经改变状态了吗？自动会更新对应的view吧

2017年1月11日 18:25
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-371953)
 | [引用](#comment-text)

雨停

 说：
                

看了代码分层与业务的分分合合，只能说js越来越趋同java了。

2017年1月18日 17:38
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-372066)
 | [引用](#comment-text)

王宏

 说：
                

这个redux有没有中文的教程

2017年1月22日 09:32
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-372257)
 | [引用](#comment-text)

[子龙](http://没有)

 说：
                

给网站整个返回顶部的功能啊

2017年2月 1日 22:11
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-372328)
 | [引用](#comment-text)

思密达

 说：
                

View 要发送多少种消息，就会有多少种 Action。如果都手写，会很麻烦。可以定义一个函数来生成 Action，这个函数就叫 Action Creator。

const ADD_TODO = '添加 TODO';

function addTodo(text) {

  return {

    type: ADD_TODO,

    text      /// --------------> 这里少了key 吧 ？？？  payload : text      

  }

}

const action = addTodo('Learn Redux');

你把井号后面的字符删掉不就上去了啊

一口老血

                

const Counter = ({ value }) => (

  {value}

  +

  -

);

阮老师，这是怎么回事，这是一个 箭头函数 返回HTML片段？

const render = () => {

  ReactDOM.render(

    
      value={store.getState()}

      onIncrement={() => store.dispatch({type: 'INCREMENT'})}

      onDecrement={() => store.dispatch({type: 'DECREMENT'})}

    />,

    document.getElementById('root')

  );

};

这里面的 Counter 又是一个 什么东西？

                

阮老师好，我查看了很多地方都没发现es6里的 ...三个点的写法您有时间时帮忙补充一下这方面的知识感谢，再次从您的播客中又得到知识财富

... state --是什么原理啊，我google不出来

const userReducer =(state={},action) => {

 state = {... state,name:action.payload}

  return state

}
   

>     引用刀尖的发言：
> 
> 
> 最后那个计数，实在不能苟同，这么写，React就不是React了，忽略了React状态机的本质

暂一个，确实如此

2017年2月22日 09:57
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-373269)
 | [引用](#comment-text)

阮哥

 说：
                

j为什么非要用es6的写法来写呢，看的人感觉很高大上，但是你忽略了大伙儿的层次，好吧，只有我最差么

2017年2月22日 09:59
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-373270)
 | [引用](#comment-text)

Mr.Ren

 说：
                

>     引用李建文的发言：
> 
> 
> 最后一个例子，Counter组件中，传入的参数不应该是{value} ,应该是{value,onIncrement,onDecrement}吧，不然，经实测，函数总报错onIncrement和onDecrement未定义。
> 
> 还有一个问题，这里之所以传入一个对象，是理解为对象的解构赋值吗，这个对象与Counter组件的属性对象相对应？

这是一个ES6语法！！！！


import { combineReducers } from 'redux';

const chatReducer = combineReducers({

  chatLog,

  statusMessage,

  userName

})

export default todoApp;

最后一行有笔误，export的不是todoApp，而应该是chatReducer

我整理看了下，感觉就是一个基于订阅发布模式，这种模式，如果在每个组件中都存在大量的dispatch，对后续维护，个人觉得很难

2017年3月31日 15:31
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-375743)
 | [引用](#comment-text)

球场铁王

 说：
                

>     引用软刀的发言：
> 
> 
> 我也没看懂。。。

这个是对象的解构，因为返回的state有三个对应的属性名

2017年4月 6日 10:49
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-375936)
 | [引用](#comment-text)

[杜少](http://www.takozhang.cn)

2017年4月 7日 15:13
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-376008)
 | [引用](#comment-text)

SunnyTuZi

 说：
                

老师，你的最后一个计时器例子运行不了，一个是Counter组件没有主标签，会报一个组件只能有一个主标签的错误，另外Counter组件中会报找不到onIncrement，onDecrement这两个属性，应该定义的是Counter组件的属性参数应该是{value,onIncrement,onDecrement}，写法：

const Counter = ({

	value,onIncrement,onDecrement

}) => (

	{value}

	 +  

	 - 

);
      

这才是如雷贯耳，网上的文章都是shit,要想明白react-native到底怎么写，必须得看阮一峰的文章，别人的文章我看不进去       

整条技术栈都快跟阮老师学完了........阮老师的BLOG每条都有用.

                

阮老师，你好，现在redux的作者都推荐了mobx，mobx相对来讲更容易上手，直观，问下是否要转到mobx还是redux使用更加便捷

2017年6月26日 11:30
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-378203)
 | [引用](#comment-text)

toong

 说：
                

>     引用atom的发言：
> 
> 
> 有一个 Redux 莞式教程 [https://github.com/kenberkeley/redux-simple-tutorial，貌似跟博主的行文差不多。。。](https://github.com/kenberkeley/redux-simple-tutorial，貌似跟博主的行文差不多。。。)

的确非常相似，但看了一下貌似是github上这个先出
        

我的哥哥，这都一年之前的文章了，我看官网redux的30个视频，愣是看到一半无法看下去看不懂，看了gitbook文章照着敲也没弄好，想找更加简单的例子便于理解，阮老师的文章对我有帮助，谢谢谢

                

我想知道 formValues 这个方法是如何用的

 说：
          
看了两天好几个教程，头都大了，困惑在基本问题上，

组件怎么绑定的action？

reducer怎么派发新的state给组件？

就是这家问题搞的十分上火，教程常常有"专家盲点"，又看了一晚上才算搞清楚，我大概总结下，或许有误，还望指证:

在组件上onclick=function(){store.dispatch({type:"动作A”，其他的数据})}就是绑定一个action；

触发后会就会调用reducer，reducer会反回一个state值；

新的值会依据store.subscribe(希望被更的新组件)传到组件"家门口"，同时在组件里用store.getState()方法读取【此刻别的组件不能访问这个值么？】


 说：
                

之前一直是用redux／reflux管理全局和需要共享的状态，组件内部不需要分享的状态组件自己管理，到新公司后发现，项目用的reflux，每个组件都有一个store，每个组件内部的状态变化都要用reflux的action触发，前端老大说redux／reflux的单向数据流就是这样。我就很困惑了，组件内不被分享的状态变化直接用setState就够了吧？既然不被分享，这些状态的变化在组件内不都是可追踪的么，一想到要用redux重写项目我就觉得头疼，每个状态变化都要写action、dispatch、reducer。。。

2017年9月 3日 22:41
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html#comment-380033)
 | [引用](#comment-text)

laden666666

 说：
                

>     引用echoloyuk的发言：
> 
> 
> 我也感觉是，计数的demo感觉靠的是刷新整个Component，忽略了React本身的状态机制。这和用jQuery重新刷新整个页面本质上没什么区别。

首先这个例子是redux官方例子，redux是全局状态管理，本身就是要尽量去除react的状态管理机制，实现单向数据流。其次这个例子和用jQuery重新刷新整个页面本质上确实没什么区别，因为这里主要是讲redux的，主要讲如何管理状态，而不是如何渲染dom，如果想看react和redux集成，请看react-redux，阮老师后面的教程有         

说再多还不如多来点实际的demo配合一起讲解，这样明白的更快些
                

有点不懂！
     

这里描述不清晰，建议去：http://redux.js.org/docs/basics/Reducers.html

                

                

const Counter = ({ value }) => (

  <h1>{value}</h1>

  <button onClick={onIncrement}>+</button>

  <button onClick={onDecrement}>-</button>

);

阮老师，关于这一部分，我有两个疑问：

一、（）内的标签是不是只能有一个外层标签？

二、这里的参数onIncrement和onDecrement是不是没有引入？

我自己在运行上面的代码时出现了这两个问题。


谢谢指出，原代码确实有你说的问题，我已经改过来了。

                

老师 网站背景色可以换一下吗？ 或者把那个暗黄色去掉吧，效果要很好，我有强迫症，每次看着都很难受。 O(∩_∩)O

/* background-color: #f5f5d5; */

                

入门的时候，看了好几遍您的redux系列文章，现在感觉也做过些demo及项目，打算重新系统学一遍redux基础，其中可能会引用您的博客内容～

                

“五、Reducer的拆分

Reducer 函数负责生成 State。由于整个应用只有一个 State 对象，包含所有数据，对于大型应用来说，这个 State 必然十分庞大，导致 Reducer 函数也十分庞大。”

  这里应该是整个应用只有一个Store对象吧，后面的State也应该是Store吧
       

看了createStore的源码，在看简单实现，不能佩服更多，赞！！！       

计数器的那个案例下载下来如何跑起来啊？

刚开始学react，对redux不了解，不知道什么时候用，多学学教程，我想，应该就能懂，谢谢阮老师。

                

开题说了react有两个问题没涉及到 其中有一个代码结构，这是为什么，不是都已经做成组件化了吗，这样不算是代码结构吗
 说：
                

大概是去年（2016）年冬天看到这篇文章，当时就Mark了，一直没下决心仔细研读；

今年（2017）又到冬天了，躲在被窝里读完后仍然很是受用，下一步继续跟进学习dva，

多谢分享知识，知识分享！ 


#### 参考 ####

