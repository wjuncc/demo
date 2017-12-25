---
layout: post
title:  "React Redux 入门教程2 中间件与异步操作 (笔记)"
date:   2017-10-08 11:21:56 +0800
categories:  
tags: 
    - react

---

from [toturial Redux 入门教程（二）：中间件与异步操作 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)


a.bshareDiv,#bsPanel,#bsMorePanel,#bshareF{border:none;background:none;padding:0;margin:0;font:12px Helvetica,Calibri,Tahoma,Arial,宋体,sans-serif;line-height:14px;}#bsPanel div,#bsMorePanel div,#bshareF div{display:block;}.bsRlogo .bsPopupAwd,.bsRlogoSel .bsPopupAwd,.bsLogo .bsPopupAwd,.bsLogoSel .bsPopupAwd{line-height:16px !important;}a.bshareDiv div,#bsFloatTab div{*display:inline;zoom:1;display:inline-block;}a.bshareDiv img,a.bshareDiv div,a.bshareDiv span,a.bshareDiv a,#bshareF table,#bshareF tr,#bshareF td{text-decoration:none;background:none;margin:0;padding:0;border:none;line-height:1.2}a.bshareDiv span{display:inline;float:none;}div.buzzButton{cursor:pointer;font-weight:bold;}.buzzButton .shareCount a{color:#333}.bsStyle1 .shareCount a{color:#fff}span.bshareText{white-space:nowrap;}span.bshareText:hover{text-decoration:underline;}a.bshareDiv .bsPromo,div.bshare-custom .bsPromo{display:none;position:absolute;z-index:100;}a.bshareDiv .bsPromo.bsPromo1,div.bshare-custom .bsPromo.bsPromo1{width:51px;height:18px;top:-18px;left:0;line-height:16px;font-size:12px !important;font-weight:normal !important;color:#fff;text-align:center;background:url(//static.bshare.cn/frame/images/bshare_box_sprite2.gif) no-repeat 0 -606px;}div.bshare-custom .bsPromo.bsPromo2{background:url(//static.bshare.cn/frame/images/bshare_promo_sprite.gif) no-repeat;cursor:pointer;}.bsBox{display:none;z-index:100000001;font-size:12px;background:url(//static.bshare.cn/frame/images//background-opaque-dark.gif) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}.bsClose{_overflow:hidden;cursor:pointer;position:absolute;z-index:10000000;color:#666;font-weight:bold;font-family:Helvetica,Arial;font-size:14px;line-height:20px;}.bsTop{color:#666;background:#f2f2f2;height:24px;line-height:24px;border-bottom:1px solid #e8e8e8;}.bsTop span{float:left;}.bsFrameDiv,#bsMorePanel{border:none;background:#fff;}.bsReturn{float:right;*margin-right:20px;margin-right:36px;text-align:right;cursor:pointer;line-height:24px;color:#666;opacity:0.5;}#bsReturn:hover{text-decoration:underline;opacity:1;}div.bsClear{clear:both;height:0;line-height:0;overflow:hidden;font-size:0;}.bsSearchDiv{padding:5px 15px;background-color:#fafafa;}.bFind-wrapper-top{background:#fff;border-color:#ccc #aaa #aaa #ccc;border-style:solid;border-width:1px;height:16px;padding:4px;margin:0;}.bFind-wrapper-top input{padding:0 !important;border:none !important;box-shadow:none !important;line-height:16px !important;}.bFind-placeholder{background:url("//static.bshare.cn/css/images/search-icon.gif") no-repeat;display:block;float:left;height:16px;width:16px;}.bFind{background:none;border:none;float:left;font-size:11px !important;height:16px !important;margin-left:3px;outline:none;padding:0;width:400px;}.bsPlatDiv{height:322px;background:#fff;overflow:auto;padding:0 15px;}#bsLogoList{display:block;list-style:none;overflow:hidden;margin:0;padding:0;}#bsLogoList li{float:left;display:inline-block;width:71px;text-align:center;font-size:12px;height:80px;margin:0 !important;}#bsLogoList .bsPlatIcon{cursor:pointer;display:block !important;text-align:center;}#bsLogoList .bsPlatImg{width:32px;height:32px;border:none !important;display:inline-block;}#bsLogoList .bsPlatImg:hover{-moz-border-radius:7px;-webkit-border-radius:7px;border-radius:7px;box-shadow:0 0 15px #a7a8ac;}#bsLogoList .bsPlatName{white-space:nowrap;text-overflow:ellipsis;overflow:hidden;text-align:center;color:#333 !important;margin-top:2px;line-height:140%;*width:70px;}#bsLogoList .bsPromoM{text-align:center;}.bsFooterDiv{height:24px;line-height:24px;padding:0 15px;border-top:1px solid #e8e8e8;background:#f2f2f2;text-align:right;}a.bsLogoLink{color:#666;}.bsLogoLink:hover{text-decoration:underline;}.bsPromoM{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;}.bsNew,.bsHot,.bsRec,.bsAwd{background-position:0 -552px;width:19px;margin:5px auto 1px;line-height:16px;height:18px;font-size:12px;color:#fff;overflow:hidden;}.bsNew{background-position:0 -570px;}.bsRec{width:30px;background-position:0 -588px;}.bsAwd{background:url(//static.bshare.cn/frame/images//promot/promote.gif) no-repeat;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}
if (/mobile/i.test(navigator.userAgent) || /android/i.test(navigator.userAgent)) document.body.classList.add('mobile');

window.addEventListener('load', function(event) {
  setTimeout(function () {
    hab('#sup-post-2');
    hab('#gd1-inner');
  }, 1000);
});

阮一峰的网络日志  » [首页](http://www.ruanyifeng.com/blog/) » [档案](http://www.ruanyifeng.com/blog/archives.html)

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAABGdBTUEAAK/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAUzSURBVHjavFdbbFRVFF3nPjoz7dTWTittaW0jUDRAUqaNojyqREnEQKgfUj9MqqAmhqRt/OCD4CuY+Kckoh+aiGKC+gMJbdHoRysJ8dkhhmJLNdDKtJU+6GMK87j3Hs85d2Z6HzNtMYWb3Dn3NWftvfba+5xNYDl+e6Fkj6yqb/oDRbWq14vlPBLRKCITkxf0ROLt+hNjp1PPSRK4kA3vF1dXNRcWlyA2OQU9eos9opAkAiKxD+XkKO6t15aRWO7J/MgmAZU8MEgexgZHMX518Dh72sYMmVKShnxWuWHdHtxKIDIYTgMuDzgfmSOIQkYMpdUF8OY92Hytt4/jvkg47czzU16iQovM3QFwmNck+Yyduu7D6NA0Z6JR4THntFs9V4tWQg6Ui3s6MwKDncsFTnXKLJhDSeUK3AgPtyhccDzmVs999buRt/1Vm4i0od+hX7+MRG87jPGB/w1u8FPj9xEw7McVrnYuOCvtpjTth3J/nTg99c8LRhKhr6D3dTB5R24bXFwbMXBsyZzeoXaycEpJ95TB09AGX/NpqLVNtw8urnVzLvHjFNxiFqRy2OOHuqUVnue+ACkoWzo4O6lGzTmuHq6nPvY2m9rVqjrIK2rMEKxqyG5NPAKt+wjo0LklgfNxJkZMA3KJvqRUk3z5UFY3QH14P0h+WUY79HPvgv7VuSg4ZRGY1YgZgqXmORccF17sy2ehnf9AeO085K2HQFbtXBScj0LcpgF2cN+WV+DZ/LJQu6gD4R7oV7pBJwbSgtMvfiPoVp56DySwxm7EtkMs1WdAB7qzggsDJKQYsHucSkOudrkiCPWR/fA2nYCn8SNIK4NptSMyAu3sAdDRkIsJdfth0LzSrODUoPNZ4KI9SxJI5UHk7D4GdQfz2us31c7CoHMjRkKuDPHseCMrONVhNcDJwMJpKFVvg9L4OaTiNWm1x789KCqkrXhVBiEz0WYCT2nAzQAD1/vaETv1GrRfP4Vx5cfMNcDPwvP0h0DhanPym7OIf/+O67vcJ1/PCJ4KgdzaUP6Wz+dU+5yIL6fV+PsHGAOdwlPpvvUOyeeAVGyCdqkDNB6DPjsBSrnndfOGevOh3RhGItxvA+fX1CtbGFhgYUFkFMZPR6F1HnClHq8HyubWtJexX06CRmdt33hrd7nA7SFY4qoGpnYuOKcRykPPgDCBcsHx9Iv+fNL2PueBehCWUfYQIIMGLOCcOmXDXsh1+yCt35tUPfvzGFuSvzvoinXOxqa02qOhM6733nVP2MAdaej2XN11DPKjLZCD+yBvahGCo7JfTKAN9UD7s8Oe9zUNIhz8fWI8DG2k38WCFdxugANcXrvTVd1IEbuv3Jour7Hzn7jLMBNfKs7R3i67gRVrbeCOEDhinmWhAatsqdquM2XzHZINhK2cqTjHr/XZdVJUbgN3MWAVXKbSyg9jesRW2xP9di+lwrL5ojM3m2H/kG9hwcIA37c71W6wJdW2J2S5nrjYbq/t1AHAhJsKQeyfPvf6IMJgghPJhFZ4x0KlfLFvt22du45Au/A1SOlGc0P672XXwhLtOcM0kTTEMMd0qkVmMNXxMd/tsedUjInr4SQDgOfeXMSiN0FCL5WHah4L1qqYXPJOJlttd+a5M+YpcG5poLYKQ5f+6JJ4r8bbJYP47hq4r7QAs9PjYNhHJd4o8l5taiwuOpa7AS4XKqI/5NjJbTnaWK92nLdLuhQAJayRNMiygXPBeQN+Qbvu0zDc3y+aUzhbkGR73sI7ljvUnndx2q3t+X8CDAD66FtrIL864AAAAABJRU5ErkJggg==)](/feed.html)

- 上一篇：[Redux 入门教程（](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)
- 下一篇：[Redux 入门教程（](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html)

分类：

- [JavaScript](http://www.ruanyifeng.com/blog/javascript/)

- [⇐ ](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)
- [ ⇒](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html)

# Redux 入门教程（二）：中间件与异步操作

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

作者： [阮一峰](http://www.ruanyifeng.com)

日期： [2016年9月20日](http://www.ruanyifeng.com/blog/2016/09/)

[![珠峰培训](http://www.ruanyifeng.com/blog/images/sponsor_zhufeng5.png)](http://www.zhufengpeixun.cn/main/course/guide.html?ref=ruanyifeng.com)

[上一篇文章](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)，我介绍了 Redux 的基本做法：用户发出 Action，Reducer 函数算出新的 State，View 重新渲染。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016092001.jpg)

但是，一个关键问题没有解决：异步操作怎么办？Action 发出以后，Reducer 立即算出 State，这叫做同步；Action 发出以后，过一段时间再执行 Reducer，这就是异步。

怎么才能 Reducer 在异步操作结束后自动执行呢？这就要用到新的工具：中间件（middleware）。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016092002.jpg)

## 一、中间件的概念

为了理解中间件，让我们站在框架作者的角度思考问题：如果要添加功能，你会在哪个环节添加？

> （1）Reducer：纯函数，只承担计算 State 的功能，不合适承担其他功能，也承担不了，因为理论上，纯函数不能进行读写操作。
> 
> （2）View：与 State 一一对应，可以看作 State 的视觉层，也不合适承担其他功能。
> 
> （3）Action：存放数据的对象，即消息的载体，只能被别人操作，自己不能进行任何操作。

想来想去，只有发送 Action 的这个步骤，即`store.dispatch()`方法，可以添加功能。举例来说，要添加日志功能，把 Action 和 State 打印出来，可以对`store.dispatch`进行如下改造。

>     let next = store.dispatch;
>     store.dispatch =functiondispatchAndLog(action){
>       console.log('dispatching', action);next(action);
>       console.log('next state', store.getState());}

上面代码中，对`store.dispatch`进行了重定义，在发送 Action 前后添加了打印功能。这就是中间件的雏形。

中间件就是一个函数，对`store.dispatch`方法进行了改造，在发出 Action 和执行 Reducer 这两步之间，添加了其他功能。

## 二、中间件的用法

本教程不涉及如何编写中间件，因为常用的中间件都有现成的，只要引用别人写好的模块即可。比如，上一节的日志中间件，就有现成的[redux-logger](https://github.com/evgenyrodionov/redux-logger)模块。这里只介绍怎么使用中间件。

>     
>     import { applyMiddleware, createStore } from 'redux';
>     import createLogger from 'redux-logger';
>     const logger =createLogger();
>     
>     const store =createStore(
>       reducer,applyMiddleware(logger));

上面代码中，`redux-logger`提供一个生成器`createLogger`，可以生成日志中间件`logger`。然后，将它放在`applyMiddleware`方法之中，传入`createStore`方法，就完成了`store.dispatch()`的功能增强。

这里有两点需要注意：

（1）`createStore`方法可以接受整个应用的初始状态作为参数，那样的话，`applyMiddleware`就是第三个参数了。

>     
>     const store =createStore(
>       reducer,
>       initial_state,applyMiddleware(logger));

（2）中间件的次序有讲究。

>     
>     const store =createStore(
>       reducer,applyMiddleware(thunk, promise, logger));

上面代码中，`applyMiddleware`方法的三个参数，就是三个中间件。有的中间件有次序要求，使用前要查一下文档。比如，`logger`就一定要放在最后，否则输出结果会不正确。

## 三、applyMiddlewares()

看到这里，你可能会问，`applyMiddlewares`这个方法到底是干什么的？

它是 Redux 的原生方法，作用是将所有中间件组成一个数组，依次执行。下面是它的源码。

>     
>     export default functionapplyMiddleware(...middlewares){return(createStore)=>(reducer, preloadedState, enhancer)=>{var store =createStore(reducer, preloadedState, enhancer);var dispatch = store.dispatch;var chain =[];var middlewareAPI ={
>           getState: store.getState,
>           dispatch:(action)=>dispatch(action)};
>         chain = middlewares.map(middleware =>middleware(middlewareAPI));
>         dispatch =compose(...chain)(store.dispatch);return{...store, dispatch}}}

上面代码中，所有中间件被放进了一个数组`chain`，然后嵌套执行，最后执行`store.dispatch`。可以看到，中间件内部（`middlewareAPI`）可以拿到`getState`和`dispatch`这两个方法。

## 四、异步操作的基本思路

理解了中间件以后，就可以处理异步操作了。

同步操作只要发出一种 Action 即可，异步操作的差别是它要发出三种 Action。

> - 操作发起时的 Action
> - 操作成功时的 Action
> - 操作失败时的 Action

以向服务器取出数据为例，三种 Action 可以有两种不同的写法。

>     
>     // 写法一：名称相同，参数不同
>     { type:'FETCH_POSTS'}{ type:'FETCH_POSTS', status:'error', error:'Oops'}{ type:'FETCH_POSTS', status:'success', response:{...}}
>     // 写法二：名称不同
>     { type:'FETCH_POSTS_REQUEST'}{ type:'FETCH_POSTS_FAILURE', error:'Oops'}{ type:'FETCH_POSTS_SUCCESS', response:{...}}

除了 Action 种类不同，异步操作的 State 也要进行改造，反映不同的操作状态。下面是 State 的一个例子。

>     let state ={ // ... 
>       isFetching:true,
>       didInvalidate:true,
>       lastUpdated:'xxxxxxx'};

上面代码中，State 的属性`isFetching`表示是否在抓取数据。`didInvalidate`表示数据是否过时，`lastUpdated`表示上一次更新时间。

现在，整个异步操作的思路就很清楚了。

> - 操作开始时，送出一个 Action，触发 State 更新为"正在操作"状态，View 重新渲染
> - 操作结束后，再送出一个 Action，触发 State 更新为"操作结束"状态，View 再一次重新渲染

## 五、redux-thunk 中间件

异步操作至少要送出两个 Action：用户触发第一个 Action，这个跟同步操作一样，没有问题；如何才能在操作结束时，系统自动送出第二个 Action 呢？

奥妙就在 Action Creator 之中。

>     
>     class AsyncApp extends Component{componentDidMount(){
>         const { dispatch, selectedPost }= this.props
>         dispatch(fetchPosts(selectedPost))}
>     // ...
>     

上面代码是一个异步组件的例子。加载成功后（`componentDidMount`方法），它送出了（`dispatch`方法）一个 Action，向服务器要求数据 `fetchPosts(selectedSubreddit)`。这里的`fetchPosts`就是 Action Creator。

下面就是`fetchPosts`的代码，关键之处就在里面。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016092003.jpg)

>     
>     const fetchPosts = postTitle =>(dispatch, getState)=>{dispatch(requestPosts(postTitle));returnfetch(`/some/API/${postTitle}.json`).then(response => response.json()).then(json =>dispatch(receivePosts(postTitle, json)));};};
>     // 使用方法一
>     store.dispatch(fetchPosts('reactjs'));
>     // 使用方法二
>     store.dispatch(fetchPosts('reactjs')).then(()=>
>       console.log(store.getState()));

上面代码中，`fetchPosts`是一个Action Creator（动作生成器），返回一个函数。这个函数执行后，先发出一个Action（`requestPosts(postTitle)`），然后进行异步操作。拿到结果后，先将结果转成 JSON 格式，然后再发出一个 Action（ `receivePosts(postTitle, json)`）。

上面代码中，有几个地方需要注意。

> （1）`fetchPosts`返回了一个函数，而普通的 Action Creator 默认返回一个对象。
> 
> （2）返回的函数的参数是`dispatch`和`getState`这两个 Redux 方法，普通的 Action Creator 的参数是 Action 的内容。
> 
> （3）在返回的函数之中，先发出一个 Action（`requestPosts(postTitle)`），表示操作开始。
> 
> （4）异步操作结束之后，再发出一个 Action（`receivePosts(postTitle, json)`），表示操作结束。

这样的处理，就解决了自动发送第二个 Action 的问题。但是，又带来了一个新的问题，Action 是由`store.dispatch`方法发送的。而`store.dispatch`方法正常情况下，参数只能是对象，不能是函数。

这时，就要使用中间件[`redux-thunk`](https://github.com/gaearon/redux-thunk)。

>     
>     import { createStore, applyMiddleware } from 'redux';
>     import thunk from 'redux-thunk';
>     import reducer from './reducers';
>     // Note: this API requires redux@>=3.1.0
>     const store =createStore(
>       reducer,applyMiddleware(thunk));

上面代码使用`redux-thunk`中间件，改造`store.dispatch`，使得后者可以接受函数作为参数。

因此，异步操作的第一种解决方案就是，写出一个返回函数的 Action Creator，然后使用`redux-thunk`中间件改造`store.dispatch`。

## 六、redux-promise 中间件

既然 Action Creator 可以返回函数，当然也可以返回其他值。另一种异步操作的解决方案，就是让 Action Creator 返回一个 Promise 对象。

这就需要使用`redux-promise`中间件。

>     
>     import { createStore, applyMiddleware } from 'redux';
>     import promiseMiddleware from 'redux-promise';
>     import reducer from './reducers';
>     
>     const store =createStore(
>       reducer,applyMiddleware(promiseMiddleware));

这个中间件使得`store.dispatch`方法可以接受 Promise 对象作为参数。这时，Action Creator 有两种写法。写法一，返回值是一个 Promise 对象。

>     
>     const fetchPosts =(dispatch, postTitle)=>newPromise(function(resolve, reject){dispatch(requestPosts(postTitle));returnfetch(`/some/API/${postTitle}.json`).then(response =>{
>              type:'FETCH_POSTS',
>              payload: response.json()});});

写法二，Action 对象的`payload`属性是一个 Promise 对象。这需要从[`redux-actions`](https://github.com/acdlite/redux-actions)模块引入`createAction`方法，并且写法也要变成下面这样。

>     
>     import { createAction } from 'redux-actions';
>     
>     class AsyncApp extends Component{componentDidMount(){
>         const { dispatch, selectedPost }= this.props
>         // 发出同步 Action
>     dispatch(requestPosts(selectedPost)); // 发出异步 Action
>     dispatch(createAction('FETCH_POSTS',fetch(`/some/API/${postTitle}.json`).then(response => response.json())));}

上面代码中，第二个`dispatch`方法发出的是异步 Action，只有等到操作结束，这个 Action 才会实际发出。注意，`createAction`的第二个参数必须是一个 Promise 对象。

看一下`redux-promise`的[源码](https://github.com/acdlite/redux-promise/blob/master/src/index.js)，就会明白它内部是怎么操作的。

>     
>     export default functionpromiseMiddleware({ dispatch }){return next => action =>{if(!isFSA(action)){returnisPromise(action)? action.then(dispatch):next(action);}returnisPromise(action.payload)? action.payload.then(
>               result =>dispatch({...action, payload: result }),
>               error =>{dispatch({...action, payload: error, error:true});return Promise.reject(error);}):next(action);};}

从上面代码可以看出，如果 Action 本身是一个 Promise，它 resolve 以后的值应该是一个 Action 对象，会被`dispatch`方法送出（`action.then(dispatch)`），但 reject 以后不会有任何动作；如果 Action 对象的`payload`属性是一个 Promise 对象，那么无论 resolve 和 reject，`dispatch`方法都会发出 Action。

中间件和异步操作，就介绍到这里。[下一篇文章](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html)将是最后一部分，介绍如何使用`react-redux`这个库。

（完）

### 文档信息

- 版权声明：自由转载-非商用-非衍生-保持署名（[创意共享3.0许可证](http://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)）
- 发表日期： 2016年9月20日
- 更多内容： [ 档案](http://www.ruanyifeng.com/blog/archives.html)  » 
[ JavaScript](http://www.ruanyifeng.com/blog/javascript/)
- 博客文集：[《前方的路》](http://road.ruanyifeng.com)，[《未来世界的幸存者》](http://survivor.ruanyifeng.com)
- 社交媒体：[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAYAAACNiR0NAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAk1JREFUeNqsVc9rE0EU/mZ3dhPNJl2bVIk/Km09aFBE8GLvnrwJXvwLxIsgCP4Fnit6E8Gb0IMHwUsL9SSNgiAoooJIpE1Joo1h82uT7IxvxmRN3Q32kAdvdrI773vfe+/bDTu9WioDcDAda3Ja8piepQ1avCkCeny0Y+R9KenKwOmHHLvPaKn7AtVOoO8dOWDCMpg+41gMQv5FNEJACgoE8MsPNLDBhgfoutMOsJDmWLmU037C4TApciljwQ/kHoohQxV06+wMXNvE7WINuaSpvdYVKLgWnl3O4zAxU3Z1IYVGT+B5qYWV9z2kbQaT/cOwTsxOUUYF+mB5Dkmi8HG3h2q9hxsFNwRTdvQgxxnXRrMvIdkEhllis/qtiWuLDm4WZnBlPoWnXz28LHdw0uGR7m9Wu3j0qYGEubfn4UlBfXO4gTZltRNMg9w9f0i7kNFxllsBlS0x75gYfxyWTBUjT2W5CSMSPBrQuG21+hiMDS8CeCzF8eSLp13uQ3Ab1IqMFZN8tFHPmgOBF99bYP8Be1Xp6t7OJszJgKpPSiZvaj7uf2hguz2IBQuozDvFH6RDBjuK9wdQDvt0nMpW+8efGyh5UcAeZb2+UcHbnz5Jx4wdlp4yJYU3kLiQtfBwOYeLc8nIwfXtNu69q2Oz4mMxbemYOOOjKarhvq51KUjg3GwiFPIuvcNF6pnSnWK0lOEabNLgQh1aJFAhlGB9rG110B2+oyRNPc0sZbRNFltmLKDKqj4Qrm1ojzOxDz2pyPQ0P7CK4c40/wJ+CzAAGYrXsvfFXR4AAAAASUVORK5CYII=) twitter](https://twitter.com/ruanyf)，[![](data:image/png;base64,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) weibo](http://weibo.com/ruanyf)
- Feed订阅： [![](data:image/gif;base64,R0lGODlhFAAUANU2APV1GfmrePZ8IeR5VPq2ieNkLf7p3NpFJveCJ/NoFfibVPR1IexiJfvdzuZrNfXGuOhUEueTevaFOfzIpNxDGeZZJNU6IOubifiVTfOnid1aLuZpLOFSJf/28vJtIvGcefaLSd5kNu9iFv/z6//48//t4uFfLfNkCeJNGuGNc/rCof/+/PVxEeldI/V5KeKMbu9nIvB2OvzQtNxMKfOPXP///wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH5BAEAADYALAAAAAAUABQAAAb/QJstEjKZCsjCZsl0pIS2QWXaYsA8noVWIEAgFoNhhWNyMESi7Jbr/aZCFdRnZJAFJCwAt+vlOkwtEBk1hDUkExJ6bQJaGyYMLTQTDSOFHQF8jAseSFYiJwkuAQ2FE1xaHjBIMDAgARguJwABJIQTLJswDEgeIgSEJQQILAqVNQEiui1HHgkBhTUGCiwYtR0xLS0VJhtaEgoEBoQkGCfPNSoQY9xaCwAsCBPALgmkJA4cZN0CAAgY/PJqEIDwgVAECjM0bOAnwcAKGQJclKhRgoGDDjUeUDigkN8vQiBOfByAglSDAxw3IBCgYEU0FyJoEPpA4UGNDjMsaHDQR8EdPVYOMmQYQGHAhQgHLIRIsWAlgASsGMRBMWMGBQtYZ7yIsoBRKkhjOMxAiXJGGCEpHGxIYsSIhrcaQmy1EQQAOw==)](/feed.html)

[![一灯学堂](http://www.ruanyifeng.com/blog/images/sup_yideng_201711a.jpg)](http://www.yidengxuetang.com/recruit?utm_source=ruanyifeng.com)

[![优达学城](http://www.ruanyifeng.com/blog/images/sup_udacity_201711c.jpg)](https://cn.udacity.com/course/react-nanodegree--nd019-cn/?utm_source=ruanyfc&amp;utm_medium=KOL&amp;utm_campaign=react)

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

## 留言（46条）

surersen

 说：
                

刚学习完阮老师的Redux 入门教程（一），写的非常通俗易懂，学习了，谢谢。

2016年9月20日 10:47
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364802)
 | [引用](#comment-text)

[Micooz](https://apporz.com)

 说：
                

Redux在处理异步轮询的业务场景时十分尴尬：

1. 应用响应用户操作，开始轮询，每隔5秒dispatch一个异步action。

2. 应用根据上一次action的reducer结果，自动改变两次状态(doing, done)。

3. 轮询期间，应用需要根据返回结果确定是否结束轮询。

麻烦就出在步骤3中，判断逻辑应该写在component中呢还是reducer中呢？

1. 写在component的render方法中显然不合适，componentWillUpdate或者componentDidUpdate也不太好，因为组件很可能受其他action的影响而改变状态，这个时候组件的判断逻辑就会变得繁琐。

2. 写在reducer中也很尴尬，这个时候reducer要控制业务逻辑，结束轮询需要调用clearInterval，这就意味着每次发action时要带上setInterval的返回值。

Redux处理一次性异步action很方便，但对于多异步action或者链式异步action，没有合适的办法进行过程控制。对于这种情形，抛开Redux使用常规方法也许是更好的选择。

不知阮老师有何建议？

2016年9月20日 10:59
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364805)
 | [引用](#comment-text)

seven

 说：
                

不错不错，下面该实践了

2016年9月20日 12:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364814)
 | [引用](#comment-text)

York

 说：
                

“奥秒就在 Action Creator 之中”，老师字打错了，应该是“奥妙”吧!

2016年9月20日 13:55
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364817)
 | [引用](#comment-text)

侯侯

 说：
                

上周直接看的官方教程没太看懂，老师写的真是简明易懂，期待下一篇

2016年9月20日 15:14
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364820)
 | [引用](#comment-text)

阮一峰

 说：
                

@York： 谢谢指出，已经改正。

@Micooz：轮询的开始和结束判断，都写在 Action Creator 里面。

2016年9月21日 13:55
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364897)
 | [引用](#comment-text)

孙梦华

 说：
                

@Micooz：

你可以在dispatch之后再返回一个promise结果，例如：

>     this.props.dispatch(login(data)).then((response) => {
>         if (response.code == 200) {
>             // do something
>         }
>     });
>     

2016年9月21日 17:20
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364905)
 | [引用](#comment-text)

[dp0qb](http://www.nioni.cn)

 说：
                

谢谢老师！！！

2016年9月21日 20:25
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-364907)
 | [引用](#comment-text)

赵越

 说：
                

很认真的拜读了您的文章，写的很赞。

对redux-promise中间件中的一段话不太理解。

如果 Action 对象的payload属性是一个 Promise 对象，那么无论 resolve 和 reject，dispatch方法都会发出 Action。  

我个人初步觉得 写法一，返回值是一个 Promise 对象，也可以在reject时发出action吧？

敬请赐教哈

2016年10月 4日 21:42
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-365667)
 | [引用](#comment-text)

cisen

 说：
                

compose真的是非常巧妙，最后生成一个洋葱剖面图的函数，dispatch(action)在最中心，中间件在两边。两句研究了半天惨研究出来，真实够厉害的。自己也真是渣T_T

2016年10月22日 22:13
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-366894)
 | [引用](#comment-text)

lazyou

 说：
                

到了第二章就看不懂了， 我到底缺少了什么技能。。。。。

2016年10月27日 10:23
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-367158)
 | [引用](#comment-text)

好炫

 说：
                

老师没看懂 

异步的话直接settimeout 然后执行dispathc不就可以了吗？

为什么需要绕一个弯，先dispatch（fn） 传入一个函数然后再在该函数内settimeout 然后再dispatch？ 这里实在是想不明白，而且我写了一下确实好像没什么不一样 希望老师指点下

2016年10月29日 10:52
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-367306)
 | [引用](#comment-text)

coolpot

 说：
                

export default function applyMiddleware(...middlewares)

问一个比较入门的问题。

请问这里的三个点是什么意思啊

2016年11月 4日 11:16
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-367750)
 | [引用](#comment-text)

超越深蓝

 说：
                

>     引用coolpot的发言：
> 
> 
> export default function applyMiddleware(...middlewares)
> 
> 问一个比较入门的问题。
> 
> 请问这里的三个点是什么意思啊

任意长参数

2016年11月 6日 14:13
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-367872)
 | [引用](#comment-text)

[onein](http://onein.cf)

 说：
                

表示没有明白要用到promise这个中间件来干什么。 获取到promise对象后干嘛用。。。

2016年11月 8日 00:26
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-367954)
 | [引用](#comment-text)

cisen

 说：
                

@Micooz:

你需要sagas

2016年11月25日 15:29
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-369171)
 | [引用](#comment-text)

laden666666

 说：
                

>     引用好炫的发言：
> 
> 
> 老师没看懂 
> 
> 异步的话直接settimeout 然后执行dispathc不就可以了吗？
> 
> 为什么需要绕一个弯，先dispatch（fn） 传入一个函数然后再在该函数内settimeout 然后再dispatch？ 这里实在是想不明白，而且我写了一下确实好像没什么不一样 希望老师指点下

两个action是为了将异步的状态信息也写入redux里面。有些项目直接可以把异步状态写到控件自己的state里面了，而有些项目是需要写到redux里面，阮老师就是讲的就是第二种情况。

如果要将异步的状态信息也写入redux里面，最少需要发两个action：第一个是同步的action，是将异步开始这个状态写入了redux；第二个action是异步方法的结果，可能是请求成功的action，也可能是失败的action，因为不可能同时成功和失败，所以阮老师说异步方法有3种action，但一次异步方法发出两种就够。

接下来阮老师说了两种方法做这件事，第一种是createAction配合redux-thunk中间件，另一种是createAction配合redux-promise中间件。这些方法好处就是你只需要调用一次就可以自动地发出这两个action，用起来比较方便。

两个方法中都没有用到settimeout，都是用promise做的，这和settimeout完全不是一回事

2016年11月26日 10:59
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-369202)
 | [引用](#comment-text)

咸鱼

 说：
                

阮老师，redux-thunk、redux-promise、redux-saga这三个异步方案孰优孰劣您有什么看法不？

2016年12月14日 20:36
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-370402)
 | [引用](#comment-text)

[lihuihero](http://无)

 说：
                

写异步的先把自己整晕了。

2016年12月15日 19:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-370461)
 | [引用](#comment-text)

MLGB

 说：
                

redux早晚得死，MLGB，搞的这么麻烦。自古以来，能在历史中一直被延续的框架，一定是操作简易的。

2016年12月28日 15:40
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-371223)
 | [引用](#comment-text)

[曹东旭](http://www.xujsp.com)

 说：
                

createAction(

      'FETCH_POSTS', 

      fetch(`/some/API/${postTitle}.json`)

        .then(response => response.json())

    )

阮老师，您这段代码create Action的调用方式是不是有问题，官网上貌似应该

createAction(

      'FETCH_POSTS')(

      fetch(`/some/API/${postTitle}.json`)

        .then(response => response.json())

    )

2017年1月 6日 11:16
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-371646)
 | [引用](#comment-text)

高峰

 说：
                

感谢老师，说的很好，可是我的理解能力有点差，慢慢体会

2017年1月16日 09:20
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-372013)
 | [引用](#comment-text)

[毛庭峰](http://lcoder.github.io)

 说：
                

这部分真的好难理解啊。表示看不懂

2017年1月20日 10:16
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-372140)
 | [引用](#comment-text)

Nesus

 说：
                

redux中的compose更新了，执行顺序从右向左。

2017年2月17日 10:24
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-373015)
 | [引用](#comment-text)

黄鑫慧

 说：
                

>     引用曹东旭的发言：
> 
> 
> createAction(
> 
> 'FETCH_POSTS', 
> 
> fetch(`/some/API/${postTitle}.json`)
> 
> .then(response => response.json())
> 
> )
> 
> 阮老师，您这段代码create Action的调用方式是不是有问题，官网上貌似应该
> 
> createAction(
> 
> 'FETCH_POSTS')(
> 
> fetch(`/some/API/${postTitle}.json`)
> 
> .then(response => response.json())
> 
> )

感谢，用这样写的方式，终于成功了

2017年3月 2日 20:04
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-373780)
 | [引用](#comment-text)

wulusai

 说：
                

大神 您学习redux参考了哪些资料 ，网址可以发出来么

2017年3月 5日 22:10
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-374019)
 | [引用](#comment-text)

三只要有你

 说：
                

阮老师，您的这块代码少加了一个括号吧，

.then(response => {

  type: 'FETCH_POSTS',

  payload: response.json()

});

.then(response => ({

  type: 'FETCH_POSTS',

  payload: response.json()

}));

2017年3月10日 18:05
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-374425)
 | [引用](#comment-text)

余皖林

 说：
                

这里应该有误：下面是官方写法

第一处、

import ReduxThunk from 'redux-thunk' // no changes here 

2017年3月31日 16:42
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-375746)
 | [引用](#comment-text)

[涛涛](http://fanwentao.duapp.com)

 说：
                

正在跟着老师学

2017年4月17日 16:41
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-376383)
 | [引用](#comment-text)

wujohns

 说：
                

这个做法好丑，还不如把异步放在外层，里层包装dispatch

2017年4月22日 14:44
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-376535)
 | [引用](#comment-text)

王一之

 说：
                

自从接触了redux，不知道代码写在哪……

2017年6月11日 21:18
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-377873)
 | [引用](#comment-text)

您的大名

 说：
                

感觉现在react这一套有点故弄玄虚，为了秀某些编程思想，想的太远了，《易》曰：“易则易知，简则易从”

2017年6月13日 17:56
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-377928)
 | [引用](#comment-text)

coderzzp

 说：
                

在中间件redux-logger这一块有一个小更新：

import createLogger from 'redux-logger';

const logger = createLogger();

现在直接引入就是一个logger，不需要再调用函数，变成如下：

import logger from 'redux-logger';

2017年8月 4日 09:37
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-379227)
 | [引用](#comment-text)

大明

 说：
                

>     引用cisen的发言：
> 
> 
> compose真的是非常巧妙，最后生成一个洋葱剖面图的函数，dispatch(action)在最中心，中间件在两边。两句研究了半天惨研究出来，真实够厉害的。自己也真是渣T_T

这叫责任链模式，compose是它的一种应用，完整的责任链的定义所有的含义更丰富。

2017年8月 4日 10:45
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-379230)
 | [引用](#comment-text)

小明

 说：
                

感觉前面写得很好，文章第六部分“redux-promise 中间件”说的好晦涩难懂，自己捋了半天都没有很明白。贴的源码也不容易看懂。

其实我觉得您可以改成，把中间件dedux-promise和promise类型的action合成一个顺序流程来讲，他们是完整的调用流程是如何的。

2017年8月 4日 12:48
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-379235)
 | [引用](#comment-text)

J

 说：
                

有人发现官网的例子，每次启动服务时，reducer都会触发三次default吗？。。

2017年8月10日 13:49
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-379418)
 | [引用](#comment-text)

[Even](http://huzhigang.top/)

 说：
                

您的教程对我很有启发，看来以后的路还长。不过相比于vuex，redux的确太麻烦了。

2017年8月11日 00:36
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-379438)
 | [引用](#comment-text)

张三

 说：
                

要不要这么复杂，这么多专业术语，表示一脸懵逼，哎...真心看不懂

2017年9月13日 17:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-380363)
 | [引用](#comment-text)

[一网友](http://zglisten.githun.io)

 说：
                

我也没看懂，不知道我缺少什么技能！函数感觉太多了，根本分不清哪些是自定义函数，哪些是库函数！仍然要感谢峰哥！

2017年9月18日 19:39
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-380595)
 | [引用](#comment-text)

ngaiwe

 说：
                

阮老师 请教问题这个Action Creator写在什么地方？是新建一个文件夹根据项目创建多个？然后分别import 。还是写在组件中？

2017年10月28日 09:07
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-381749)
 | [引用](#comment-text)

wongjorie

 说：
                

勘误 => applyMiddleware()

2017年11月 7日 14:22
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-382083)
 | [引用](#comment-text)

water

 说：
                

作者在介绍redux-thunk中间件的用法的时,介绍store.dispatch()的参数是一个函数,结合作者的代码:return fetch(`/some/API/${postTitle}.json`)

    .then(response => response.json())

    .then(json => dispatch(receivePosts(postTitle, json))).

但是fetch().then() return的结果是一个函数吗?

2017年11月 9日 16:45
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-382199)
 | [引用](#comment-text)

june

 说：
                

>     引用coolpot的发言：
> 
> 
> export default function applyMiddleware(...middlewares)
> 
> 问一个比较入门的问题。
> 
> 请问这里的三个点是什么意思啊

es6 里的解构

2017年12月 6日 17:23
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-383027)
 | [引用](#comment-text)

kj huang

 说：
                

我有以下的疑问，求解答：

的确,redux thunk让我们从直接返回一个action object变成可以返回一个函数F。而在这个函数里我们可以做更多的事情，那这个函数F本身返回什么重要吗？有什么意义呢？

就比如阮老师的例子里

 return fetch(`/some/API/${postTitle}.json`)

    .then(response => response.json())

    .then(json => dispatch(receivePosts(postTitle, json)));

  };

这里把return去掉照样可以。

2017年12月 7日 08:20
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-383038)
 | [引用](#comment-text)

小冶

 说：
                

@kj huang：

形成Promise链式调用 ，后面可以接着继续.then()

2017年12月11日 00:57
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-383131)
 | [引用](#comment-text)

小鱼儿

 说：
                

阮老师您可否写篇redux-saga的文章，网上的资料看不太懂

2017年12月21日 14:38
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html#comment-383423)
 | [引用](#comment-text)

## 我要发表看法

您的留言
                    （HTML标签部分可用）

您的大名：

 «-必填

电子邮件：

 «-必填，不公开

个人网址：

 «-我信任你，不会填写广告链接

记住个人信息？

**正在发表您的评论，请稍候**

 «- 点击按钮

[微博](http://weibo.com/ruanyf) | [推特](https://twitter.com/ruanyf) | [GitHub](https://github.com/ruanyf)

2017 © [我的邮件](/contact.html) |

  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-46829782-1', 'ruanyifeng.com');
  ga('send', 'pageview');

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

document.getElementById("share_button").innerHTML=document.getElementById("share_button_proto").innerHTML;

X

选择其他平台 >>
分享到

[分享到...](http://www.bshare.cn/intro)[X](X)

[
Facebook
](javascript:;)

[
Twitter
](javascript:;)

[
新浪微博
](javascript:;)

[微信](javascript:;)

[腾讯微博](javascript:;)

[豆瓣网](javascript:;)

[饭否](javascript:;)

[雪球](javascript:;)

[电子邮件](javascript:;)

[Google+](javascript:;)

[QQ空间](javascript:;)

[QQ好友](javascript:;)

[Instapaper](javascript:;)

[美味书签](javascript:;)

更多平台... (133)

[bShare](http://www.bshare.cn)

