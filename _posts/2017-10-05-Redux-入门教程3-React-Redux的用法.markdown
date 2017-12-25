---
layout: post
title:  "Redux 入门教程3 React-Redux的用法"
date:   2017-10-05 11:21:56 +0800
categories:  
tags: 
    - react

---

from [toturial](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html)

Redux 入门教程（三）：React-Redux 的用法 - 阮一峰的网络日志a.bshareDiv,#bsPanel,#bsMorePanel,#bshareF{border:none;background:none;padding:0;margin:0;font:12px Helvetica,Calibri,Tahoma,Arial,宋体,sans-serif;line-height:14px;}#bsPanel div,#bsMorePanel div,#bshareF div{display:block;}.bsRlogo .bsPopupAwd,.bsRlogoSel .bsPopupAwd,.bsLogo .bsPopupAwd,.bsLogoSel .bsPopupAwd{line-height:16px !important;}a.bshareDiv div,#bsFloatTab div{*display:inline;zoom:1;display:inline-block;}a.bshareDiv img,a.bshareDiv div,a.bshareDiv span,a.bshareDiv a,#bshareF table,#bshareF tr,#bshareF td{text-decoration:none;background:none;margin:0;padding:0;border:none;line-height:1.2}a.bshareDiv span{display:inline;float:none;}div.buzzButton{cursor:pointer;font-weight:bold;}.buzzButton .shareCount a{color:#333}.bsStyle1 .shareCount a{color:#fff}span.bshareText{white-space:nowrap;}span.bshareText:hover{text-decoration:underline;}a.bshareDiv .bsPromo,div.bshare-custom .bsPromo{display:none;position:absolute;z-index:100;}a.bshareDiv .bsPromo.bsPromo1,div.bshare-custom .bsPromo.bsPromo1{width:51px;height:18px;top:-18px;left:0;line-height:16px;font-size:12px !important;font-weight:normal !important;color:#fff;text-align:center;background:url(//static.bshare.cn/frame/images/bshare_box_sprite2.gif) no-repeat 0 -606px;}div.bshare-custom .bsPromo.bsPromo2{background:url(//static.bshare.cn/frame/images/bshare_promo_sprite.gif) no-repeat;cursor:pointer;}.bsBox{display:none;z-index:100000001;font-size:12px;background:url(//static.bshare.cn/frame/images//background-opaque-dark.gif) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}.bsClose{_overflow:hidden;cursor:pointer;position:absolute;z-index:10000000;color:#666;font-weight:bold;font-family:Helvetica,Arial;font-size:14px;line-height:20px;}.bsTop{color:#666;background:#f2f2f2;height:24px;line-height:24px;border-bottom:1px solid #e8e8e8;}.bsTop span{float:left;}.bsFrameDiv,#bsMorePanel{border:none;background:#fff;}.bsReturn{float:right;*margin-right:20px;margin-right:36px;text-align:right;cursor:pointer;line-height:24px;color:#666;opacity:0.5;}#bsReturn:hover{text-decoration:underline;opacity:1;}div.bsClear{clear:both;height:0;line-height:0;overflow:hidden;font-size:0;}.bsSearchDiv{padding:5px 15px;background-color:#fafafa;}.bFind-wrapper-top{background:#fff;border-color:#ccc #aaa #aaa #ccc;border-style:solid;border-width:1px;height:16px;padding:4px;margin:0;}.bFind-wrapper-top input{padding:0 !important;border:none !important;box-shadow:none !important;line-height:16px !important;}.bFind-placeholder{background:url("//static.bshare.cn/css/images/search-icon.gif") no-repeat;display:block;float:left;height:16px;width:16px;}.bFind{background:none;border:none;float:left;font-size:11px !important;height:16px !important;margin-left:3px;outline:none;padding:0;width:400px;}.bsPlatDiv{height:322px;background:#fff;overflow:auto;padding:0 15px;}#bsLogoList{display:block;list-style:none;overflow:hidden;margin:0;padding:0;}#bsLogoList li{float:left;display:inline-block;width:71px;text-align:center;font-size:12px;height:80px;margin:0 !important;}#bsLogoList .bsPlatIcon{cursor:pointer;display:block !important;text-align:center;}#bsLogoList .bsPlatImg{width:32px;height:32px;border:none !important;display:inline-block;}#bsLogoList .bsPlatImg:hover{-moz-border-radius:7px;-webkit-border-radius:7px;border-radius:7px;box-shadow:0 0 15px #a7a8ac;}#bsLogoList .bsPlatName{white-space:nowrap;text-overflow:ellipsis;overflow:hidden;text-align:center;color:#333 !important;margin-top:2px;line-height:140%;*width:70px;}#bsLogoList .bsPromoM{text-align:center;}.bsFooterDiv{height:24px;line-height:24px;padding:0 15px;border-top:1px solid #e8e8e8;background:#f2f2f2;text-align:right;}a.bsLogoLink{color:#666;}.bsLogoLink:hover{text-decoration:underline;}.bsPromoM{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;}.bsNew,.bsHot,.bsRec,.bsAwd{background-position:0 -552px;width:19px;margin:5px auto 1px;line-height:16px;height:18px;font-size:12px;color:#fff;overflow:hidden;}.bsNew{background-position:0 -570px;}.bsRec{width:30px;background-position:0 -588px;}.bsAwd{background:url(//static.bshare.cn/frame/images//promot/promote.gif) no-repeat;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}a.bsSiteLink{text-decoration:none;color:#666;}a.bsSiteLink:hover{text-decoration:underline;}a.bshareDiv{overflow:hidden;height:16px;line-height:18px;font-size:14px;color:#333;padding-left:0;}a.bshareDiv:hover{text-decoration:none;}div.bsTitle{padding:0 8px;border-bottom:1px solid #e8e8e8;color:#666;background:#f2f2f2;text-align:left;}div.buzzButton{cursor:pointer;}div.bsRlogo,div.bsRlogoSel{width:68px;float:left;margin:0;padding:2px 0;}div.bsRlogo a,div.bsRlogoSel a{float:left;}div.bsLogo,div.bsLogoSel{float:left;width:111px;text-align:left;height:auto;padding:2px 4px;margin:2px 0;white-space:nowrap;overflow:hidden;}div.bsLogoSel,div.bsRlogoSel{border:1px solid #ddd;background:#f1f1f1;}div.bsLogo,div.bsRlogo{border:1px solid #fff;background:#fff;}div.bsLogo a,div.bsLogoSel a{display:block;height:16px;line-height:16px;padding:0 0 0 24px;text-decoration:none;float:left;overflow:hidden;}div.bsLogoSel a,div.bsRlogoSel a{color:#000;border:none;}div.bsLogo a,div.bsRlogo a{color:#666;border:none;}div.bsLogoLink{width:121px;overflow:hidden;background:#FFF;float:left;margin:3px 0;}#bsLogin{float:right;text-align:right;overflow:hidden;height:100%;}#bsPanel{position:absolute;z-index:100000000;font-size:12px;width:258px;background:url(//static.bshare.cn/frame/images/background-opaque-dark.png) !important;padding:6px !important;-moz-border-radius:5px;-webkit-border-radius:5px;border-radius:5px;}div.bsClear{clear:both;height:0;line-height:0;font-size:0;overflow:hidden;}div.bsPopupAwd{background:url(//static.bshare.cn/frame/images//bshare_box_sprite2.gif) no-repeat top left;background-position:0 -624px;width:18px;padding-left:3px;text-align:center;float:left;margin-left: 2px;height:15px;font-size:12px;color:#fff;overflow:hidden;}div.bsRlogo .bsPopupAwd,div.bsRlogoSel .bsPopupAwd{float:left;margin:5px 0 0 -14px;}
if (/mobile/i.test(navigator.userAgent) || /android/i.test(navigator.userAgent)) document.body.classList.add('mobile');

window.addEventListener('load', function(event) {
  setTimeout(function () {
    hab('#sup-post-2');
    hab('#gd1-inner');
  }, 1000);
});

阮一峰的网络日志  » [首页](http://www.ruanyifeng.com/blog/) » [档案](http://www.ruanyifeng.com/blog/archives.html)

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAABGdBTUEAAK/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAUzSURBVHjavFdbbFRVFF3nPjoz7dTWTittaW0jUDRAUqaNojyqREnEQKgfUj9MqqAmhqRt/OCD4CuY+Kckoh+aiGKC+gMJbdHoRysJ8dkhhmJLNdDKtJU+6GMK87j3Hs85d2Z6HzNtMYWb3Dn3NWftvfba+5xNYDl+e6Fkj6yqb/oDRbWq14vlPBLRKCITkxf0ROLt+hNjp1PPSRK4kA3vF1dXNRcWlyA2OQU9eos9opAkAiKxD+XkKO6t15aRWO7J/MgmAZU8MEgexgZHMX518Dh72sYMmVKShnxWuWHdHtxKIDIYTgMuDzgfmSOIQkYMpdUF8OY92Hytt4/jvkg47czzU16iQovM3QFwmNck+Yyduu7D6NA0Z6JR4THntFs9V4tWQg6Ui3s6MwKDncsFTnXKLJhDSeUK3AgPtyhccDzmVs999buRt/1Vm4i0od+hX7+MRG87jPGB/w1u8FPj9xEw7McVrnYuOCvtpjTth3J/nTg99c8LRhKhr6D3dTB5R24bXFwbMXBsyZzeoXaycEpJ95TB09AGX/NpqLVNtw8urnVzLvHjFNxiFqRy2OOHuqUVnue+ACkoWzo4O6lGzTmuHq6nPvY2m9rVqjrIK2rMEKxqyG5NPAKt+wjo0LklgfNxJkZMA3KJvqRUk3z5UFY3QH14P0h+WUY79HPvgv7VuSg4ZRGY1YgZgqXmORccF17sy2ehnf9AeO085K2HQFbtXBScj0LcpgF2cN+WV+DZ/LJQu6gD4R7oV7pBJwbSgtMvfiPoVp56DySwxm7EtkMs1WdAB7qzggsDJKQYsHucSkOudrkiCPWR/fA2nYCn8SNIK4NptSMyAu3sAdDRkIsJdfth0LzSrODUoPNZ4KI9SxJI5UHk7D4GdQfz2us31c7CoHMjRkKuDPHseCMrONVhNcDJwMJpKFVvg9L4OaTiNWm1x789KCqkrXhVBiEz0WYCT2nAzQAD1/vaETv1GrRfP4Vx5cfMNcDPwvP0h0DhanPym7OIf/+O67vcJ1/PCJ4KgdzaUP6Wz+dU+5yIL6fV+PsHGAOdwlPpvvUOyeeAVGyCdqkDNB6DPjsBSrnndfOGevOh3RhGItxvA+fX1CtbGFhgYUFkFMZPR6F1HnClHq8HyubWtJexX06CRmdt33hrd7nA7SFY4qoGpnYuOKcRykPPgDCBcsHx9Iv+fNL2PueBehCWUfYQIIMGLOCcOmXDXsh1+yCt35tUPfvzGFuSvzvoinXOxqa02qOhM6733nVP2MAdaej2XN11DPKjLZCD+yBvahGCo7JfTKAN9UD7s8Oe9zUNIhz8fWI8DG2k38WCFdxugANcXrvTVd1IEbuv3Jour7Hzn7jLMBNfKs7R3i67gRVrbeCOEDhinmWhAatsqdquM2XzHZINhK2cqTjHr/XZdVJUbgN3MWAVXKbSyg9jesRW2xP9di+lwrL5ojM3m2H/kG9hwcIA37c71W6wJdW2J2S5nrjYbq/t1AHAhJsKQeyfPvf6IMJgghPJhFZ4x0KlfLFvt22du45Au/A1SOlGc0P672XXwhLtOcM0kTTEMMd0qkVmMNXxMd/tsedUjInr4SQDgOfeXMSiN0FCL5WHah4L1qqYXPJOJlttd+a5M+YpcG5poLYKQ5f+6JJ4r8bbJYP47hq4r7QAs9PjYNhHJd4o8l5taiwuOpa7AS4XKqI/5NjJbTnaWK92nLdLuhQAJayRNMiygXPBeQN+Qbvu0zDc3y+aUzhbkGR73sI7ljvUnndx2q3t+X8CDAD66FtrIL864AAAAABJRU5ErkJggg==)](/feed.html)

- 上一篇：[Redux 入门教程（](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)
- 下一篇：[React 技术栈系列](http://www.ruanyifeng.com/blog/2016/09/react-technology-stack.html)

分类：

- [JavaScript](http://www.ruanyifeng.com/blog/javascript/)

- [⇐ ](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)
- [ ⇒](http://www.ruanyifeng.com/blog/2016/09/react-technology-stack.html)

# Redux 入门教程（三）：React-Redux 的用法

[http://www.bshare.cn/share](http://www.bshare.cn/share)
bShare.addEntry({
    title: document.getElementById("page-title").innerHTML,
url:window.location.href
});

作者： [阮一峰](http://www.ruanyifeng.com)

日期： [2016年9月21日](http://www.ruanyifeng.com/blog/2016/09/)

[![珠峰培训](http://www.ruanyifeng.com/blog/images/sponsor_zhufeng5.png)](http://www.zhufengpeixun.cn/main/course/guide.html?ref=ruanyifeng.com)

前两篇教程介绍了 Redux 的[基本用法](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)和[异步操作](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)，今天是最后一部分，介绍如何在 React 项目中使用 Redux。

为了方便使用，Redux 的作者封装了一个 React 专用的库 [React-Redux](https://github.com/reactjs/react-redux)，本文主要介绍它。

这个库是可以选用的。实际项目中，你应该权衡一下，是直接使用 Redux，还是使用 React-Redux。后者虽然提供了便利，但是需要掌握额外的 API，并且要遵守它的组件拆分规范。

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016092101.jpg)

## 一、UI 组件

React-Redux 将所有组件分成两大类：UI 组件（presentational component）和容器组件（container component）。

UI 组件有以下几个特征。

> - 只负责 UI 的呈现，不带有任何业务逻辑
> - 没有状态（即不使用`this.state`这个变量）
> - 所有数据都由参数（`this.props`）提供
> - 不使用任何 Redux 的 API

下面就是一个 UI 组件的例子。

>     
>     const Title =
>       value =><h1>{value}</h1>;

因为不含有状态，UI 组件又称为"纯组件"，即它纯函数一样，纯粹由参数决定它的值。

## 二、容器组件

容器组件的特征恰恰相反。

> - 负责管理数据和业务逻辑，不负责 UI 的呈现
> - 带有内部状态
> - 使用 Redux 的 API

总之，只要记住一句话就可以了：UI 组件负责 UI 的呈现，容器组件负责管理数据和逻辑。

你可能会问，如果一个组件既有 UI 又有业务逻辑，那怎么办？回答是，将它拆分成下面的结构：外面是一个容器组件，里面包了一个UI 组件。前者负责与外部的通信，将数据传给后者，由后者渲染出视图。

React-Redux 规定，所有的 UI 组件都由用户提供，容器组件则是由 React-Redux 自动生成。也就是说，用户负责视觉层，状态管理则是全部交给它。

## 三、connect()

React-Redux 提供`connect`方法，用于从 UI 组件生成容器组件。`connect`的意思，就是将这两种组件连起来。

>     
>     import { connect } from 'react-redux'
>     const VisibleTodoList =connect()(TodoList);

上面代码中，`TodoList`是 UI 组件，`VisibleTodoList`就是由 React-Redux 通过`connect`方法自动生成的容器组件。

但是，因为没有定义业务逻辑，上面这个容器组件毫无意义，只是 UI 组件的一个单纯的包装层。为了定义业务逻辑，需要给出下面两方面的信息。

> （1）输入逻辑：外部的数据（即`state`对象）如何转换为 UI 组件的参数
> 
> （2）输出逻辑：用户发出的动作如何变为 Action 对象，从 UI 组件传出去。

因此，`connect`方法的完整 API 如下。

>     
>     import { connect } from 'react-redux'
>     
>     const VisibleTodoList =connect(
>       mapStateToProps,
>       mapDispatchToProps
>     )(TodoList)

上面代码中，`connect`方法接受两个参数：`mapStateToProps`和`mapDispatchToProps`。它们定义了 UI 组件的业务逻辑。前者负责输入逻辑，即将`state`映射到 UI 组件的参数（`props`），后者负责输出逻辑，即将用户对 UI 组件的操作映射成 Action。

### 四、mapStateToProps()

`mapStateToProps`是一个函数。它的作用就是像它的名字那样，建立一个从（外部的）`state`对象到（UI 组件的）`props`对象的映射关系。

作为函数，`mapStateToProps`执行后应该返回一个对象，里面的每一个键值对就是一个映射。请看下面的例子。

>     
>     const mapStateToProps =(state)=>{return{
>         todos:getVisibleTodos(state.todos, state.visibilityFilter)}}

上面代码中，`mapStateToProps`是一个函数，它接受`state`作为参数，返回一个对象。这个对象有一个`todos`属性，代表 UI 组件的同名参数，后面的`getVisibleTodos`也是一个函数，可以从`state`算出 `todos` 的值。

下面就是`getVisibleTodos`的一个例子，用来算出`todos`。

>     
>     const getVisibleTodos =(todos, filter)=>{
>       switch (filter){
>         case 'SHOW_ALL':return todos
>         case 'SHOW_COMPLETED':return todos.filter(t => t.completed)
>         case 'SHOW_ACTIVE':return todos.filter(t =>!t.completed)
>         default:thrownewError('Unknown filter: '+ filter)}}

`mapStateToProps`会订阅 Store，每当`state`更新的时候，就会自动执行，重新计算 UI 组件的参数，从而触发 UI 组件的重新渲染。

`mapStateToProps`的第一个参数总是`state`对象，还可以使用第二个参数，代表容器组件的`props`对象。

>     
>     // 容器组件的代码
>     //    <FilterLink filter="SHOW_ALL">
>     //      All
>     //    </FilterLink>
>     
>     const mapStateToProps =(state, ownProps)=>{return{
>         active: ownProps.filter === state.visibilityFilter
>       }}

使用`ownProps`作为参数后，如果容器组件的参数发生变化，也会引发 UI 组件重新渲染。

`connect`方法可以省略`mapStateToProps`参数，那样的话，UI 组件就不会订阅Store，就是说 Store 的更新不会引起 UI 组件的更新。

## 五、mapDispatchToProps()

`mapDispatchToProps`是`connect`函数的第二个参数，用来建立 UI 组件的参数到`store.dispatch`方法的映射。也就是说，它定义了哪些用户的操作应该当作 Action，传给 Store。它可以是一个函数，也可以是一个对象。

如果`mapDispatchToProps`是一个函数，会得到`dispatch`和`ownProps`（容器组件的`props`对象）两个参数。

>     
>     const mapDispatchToProps =(
>       dispatch,
>       ownProps
>     )=>{return{
>         onClick:()=>{dispatch({
>             type:'SET_VISIBILITY_FILTER',
>             filter: ownProps.filter
>           });}};}

从上面代码可以看到，`mapDispatchToProps`作为函数，应该返回一个对象，该对象的每个键值对都是一个映射，定义了 UI 组件的参数怎样发出 Action。

如果`mapDispatchToProps`是一个对象，它的每个键名也是对应 UI 组件的同名参数，键值应该是一个函数，会被当作 Action creator ，返回的 Action 会由 Redux 自动发出。举例来说，上面的`mapDispatchToProps`写成对象就是下面这样。

>     
>     const mapDispatchToProps ={
>       onClick:(filter)=>{
>         type:'SET_VISIBILITY_FILTER',
>         filter: filter
>       };}

## 六、<Provider> 组件

`connect`方法生成容器组件以后，需要让容器组件拿到`state`对象，才能生成 UI 组件的参数。

一种解决方法是将`state`对象作为参数，传入容器组件。但是，这样做比较麻烦，尤其是容器组件可能在很深的层级，一级级将`state`传下去就很麻烦。

React-Redux 提供`Provider`组件，可以让容器组件拿到`state`。

>     
>     import { Provider } from 'react-redux'
>     import { createStore } from 'redux'
>     import todoApp from './reducers'
>     import App from './components/App'let store =createStore(todoApp);render(<Provider store={store}><App /></Provider>,
>       document.getElementById('root'))

上面代码中，`Provider`在根组件外面包了一层，这样一来，`App`的所有子组件就默认都可以拿到`state`了。

它的原理是`React`组件的[`context`](https://facebook.github.io/react/docs/context.html)属性，请看源码。

>     
>     class Provider extends Component{getChildContext(){return{
>           store: this.props.store
>         };}render(){return this.props.children;}}
>     
>     Provider.childContextTypes ={
>       store: React.PropTypes.object
>     }

上面代码中，`store`放在了上下文对象`context`上面。然后，子组件就可以从`context`拿到`store`，代码大致如下。

>     
>     class VisibleTodoList extends Component{componentDidMount(){
>         const { store }= this.context;
>         this.unsubscribe = store.subscribe(()=>
>           this.forceUpdate());}render(){
>         const props = this.props;
>         const { store }= this.context;
>         const state = store.getState(); // ...
>     }}
>     
>     VisibleTodoList.contextTypes ={
>       store: React.PropTypes.object
>     }

`React-Redux`自动生成的容器组件的代码，就类似上面这样，从而拿到`store`。

## 七、实例：计数器

我们来看一个实例。下面是一个计数器组件，它是一个纯的 UI 组件。

>     
>     class Counter extends Component{render(){
>         const { value, onIncreaseClick }= this.props
>         return(<div><span>{value}</span><button onClick={onIncreaseClick}>Increase</button></div>)}}

上面代码中，这个 UI 组件有两个参数：`value`和`onIncreaseClick`。前者需要从`state`计算得到，后者需要向外发出 Action。

接着，定义`value`到`state`的映射，以及`onIncreaseClick`到`dispatch`的映射。

>     functionmapStateToProps(state){return{
>         value: state.count
>       }}functionmapDispatchToProps(dispatch){return{
>         onIncreaseClick:()=>dispatch(increaseAction)}}
>     // Action Creator
>     const increaseAction ={ type:'increase'}

然后，使用`connect`方法生成容器组件。

>     
>     const App =connect(
>       mapStateToProps,
>       mapDispatchToProps
>     )(Counter)

然后，定义这个组件的 Reducer。

>     
>     // Reducer
>     functioncounter(state ={ count:0}, action){
>       const count = state.count
>       switch (action.type){
>         case 'increase':return{ count: count +1}
>         default:return state
>       }}

最后，生成`store`对象，并使用`Provider`在根组件外面包一层。

>     
>     import { loadState, saveState } from './localStorage';
>     
>     const persistedState =loadState();
>     const store =createStore(
>       todoApp,
>       persistedState
>     );
>     
>     store.subscribe(throttle(()=>{saveState({
>         todos: store.getState().todos,})},1000))
>     
>     ReactDOM.render(<Provider store={store}><App /></Provider>,
>       document.getElementById('root'));

完整的代码看[这里](https://github.com/jackielii/simplest-redux-example/blob/master/index.js)。

## 八、React-Router 路由库

使用`React-Router`的项目，与其他项目没有不同之处，也是使用`Provider`在`Router`外面包一层，毕竟`Provider`的唯一功能就是传入`store`对象。

>     
>     const Root =({ store })=>(<Provider store={store}><Router><Route path="/" component={App}/></Router></Provider>);

（完）

### 文档信息

- 版权声明：自由转载-非商用-非衍生-保持署名（[创意共享3.0许可证](http://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)）
- 发表日期： 2016年9月21日
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

## 留言（68条）

羽风

 说：
                

第三点的

三、conect()

拼写错了

2016年9月22日 09:49
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364914)
 | [引用](#comment-text)

阮一峰

 说：
                

@羽风：谢谢指出，已经改正。

2016年9月22日 11:16
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364920)
 | [引用](#comment-text)

Will

 说：
                

有一点不是特别明白：

store.subscribe(throttle(() => {

  saveState({

    todos: store.getState().todos,

  })

}, 1000))

这里store.subscribe时，本来只要state有变化就会执行吧，为啥还要再使用throttle呢？

是有什么考虑吗？

2016年9月22日 11:34
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364921)
 | [引用](#comment-text)

Will

 说：
                

哦，我理解了，是怕性能问题，避免调用太频繁。

2016年9月22日 12:05
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364922)
 | [引用](#comment-text)

冰冰

 说：
                

简单明了，大赞~

2016年9月22日 14:46
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364927)
 | [引用](#comment-text)

[Min](http://blog.sohappy.cc)

 说：
                

‘容器组件则是由 React-React 自动生成’

这里应该是React-Redux

2016年9月22日 17:19
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364956)
 | [引用](#comment-text)

爱吃土豆

 说：
                

Redux 入门教程（三）真是通俗易懂，让我茅塞顿开,给阮老师点个赞！么么哒

2016年9月22日 17:37
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364960)
 | [引用](#comment-text)

阮一峰

 说：
                

@Min：谢谢指出，已经改正。

2016年9月22日 19:48
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-364973)
 | [引用](#comment-text)

拖鞋酱

 说：
                

之前在github上看了好几个入门教程,都不是很明白.

当时flux就是从阮老师这儿看懂的.给阮老师点赞.

2016年9月27日 21:56
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-365286)
 | [引用](#comment-text)

[迹忆](http://www.onmpw.com)

 说：
                

给阮老师点个赞

2016年9月29日 16:37
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-365415)
 | [引用](#comment-text)

[丢丢](http://null)

 说：
                

峰哥可以搞一个大赏功能，想给你大赏都不知道往哪打

2016年9月30日 10:35
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-365467)
 | [引用](#comment-text)

小媒体

 说：
                

很赞，多谢！阮老师的页面风格看着都比较权威。

2016年9月30日 16:10
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-365479)
 | [引用](#comment-text)

McDu

 说：
                

> 这个对象有一个todos属性，代表 UI 组件的同名参数，
> 这句话怎么理解？

2016年10月 5日 18:12
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-365729)
 | [引用](#comment-text)

少安

 说：
                

求下一篇有    react redux 后台渲染的文章啊

2016年10月11日 17:28
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366136)
 | [引用](#comment-text)

tangyz

 说：
                

最后使用Provider在根组件外面包一层的代码，用的是todo的，不是计算器的了

2016年10月11日 18:02
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366140)
 | [引用](#comment-text)

BigBrother5

 说：
                

感谢阮老师，茅塞顿开！

2016年10月14日 17:50
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366367)
 | [引用](#comment-text)

bbfish

 说：
                

>     引用丢丢的发言：
> 
> 
> 峰哥可以搞一个大赏功能，想给你大赏都不知道往哪打

支持，确实比其它的资料更容易懂

2016年10月14日 18:33
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366370)
 | [引用](#comment-text)

[Kimi](http://masy.site)

 说：
                

七：实例 计数器中

    const store = createStore(
      counter, //原为todoApp
      persistedState
    );
    
    
    store.subscribe(throttle(() => {
    
      saveState({
    
        //todos: store.getState().todos,
    
        count: store.getState().count
    
      })
    
    }, 1000))
    
    

2016年10月15日 01:01
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366377)
 | [引用](#comment-text)

山水一程

 说：
                

React-Redux提供的例子：https://github.com/jackielii/simplest-redux-example 是用python运行的。我把例子代码放到webpack环境下了，地址：https://github.com/cag2050/react_redux_demo161019 ，需要的同学，可以看下。

2016年10月19日 19:15
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366678)
 | [引用](#comment-text)

chris

 说：
                

请问store.subscribe和mapStateToProps有什么关系吗？

2016年10月20日 00:01
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366686)
 | [引用](#comment-text)

[刘俊杰](http://暂无)

 说：
                

阮一峰老师每篇关于react及其技术栈的文章都拯救了我。。！！！！！

2016年10月20日 14:03
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-366743)
 | [引用](#comment-text)

[lemonleo](http://www.lemonleo.com)

 说：
                

阮老师好~  想请教个问题： 当组件第一次渲染的时候  并没有看见哪里触发了dispatch，那是怎么更新的UI呢？  是react默认第一次会自动触发dispatch吗？

2016年10月24日 21:14
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-367028)
 | [引用](#comment-text)

[steve young](https://github.com/BuptStEve)

 说：
                

>     引用chris的发言：
> 
> 
> 请问store.subscribe和mapStateToProps有什么关系吗？

是在高阶组件（connect 函数返回的组件）里的 componentDidMount 订阅 store 更新，和 componentWillUnmount 取消订阅。（还有声明 contextTypes...）

安利下我的学习笔记...～=￣ω￣=～

[http://buptsteve.github.io/blog/2016/10/25/7.react-and-redux-learning-note-basics/](http://buptsteve.github.io/blog/2016/10/25/7.react-and-redux-learning-note-basics/)

2016年10月26日 23:09
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-367157)
 | [引用](#comment-text)

test

 说：
                

 AddTodo

像这种需要将input的内容dispatch出去的要如何划分成ui组件和容器组件呢？

2016年10月30日 12:38
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-367370)
 | [引用](#comment-text)

chris

 说：
                

>     引用steve young的发言：
> 
> 
> 是在高阶组件（connect 函数返回的组件）里的 componentDidMount 订阅 store 更新，和 componentWillUnmount 取消订阅。（还有声明 contextTypes...）
> 
> 安利下我的学习笔记...～=￣ω￣=～
> 
> [http://buptsteve.github.io/blog/2016/10/25/7.react-and-redux-learning-note-basics/](http://buptsteve.github.io/blog/2016/10/25/7.react-and-redux-learning-note-basics/)

感谢，关于官网的real-world示例，有一些问题，不知道可否请教下~

2016年11月 8日 01:27
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-367955)
 | [引用](#comment-text)

Grubby

 说：
                

const mapDispatchToProps = {

  onClick: (filter) => {

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  };

}

这一句的话，箭头函数返回一个对象对象不用（）包起来不会报错吗？

2016年11月 9日 15:03
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-368066)
 | [引用](#comment-text)

朱砂变

 说：
                

mapStateToProps会订阅 Store，每当state更新的时候，就会自动执行，重新计算 UI 组件的参数，从而触发 UI 组件的重新渲染。

阮老师，在react-redux v4.4.5版本的connect函数中，并没有找到mapStateToProps订阅Store的行为，请问您上面说的那句话该如何理解？

2016年11月12日 16:48
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-368241)
 | [引用](#comment-text)

[czj](https://github.com/zhongjie-chen)

 说：
                

比如一个简单的状态 现实隐藏某个组件 类似这种状态也要放到给redux管理吗 这个应该属于ui组件 具体在项目中应该如何划分呢？

2016年11月20日 20:27
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-368805)
 | [引用](#comment-text)

[jarson](http://luckykun.com)

 说：
                

阮老师：mapStateToProps使用ownProps作为参数后，如果容器组件的参数发生变化，也会引发 UI 组件重新渲染。

var num = 0;

ReactDom.render((

    <Provider store={store}>

        <MyCounter num={num}/>

    </Provider>

), document.getElementById('app'));

setTimeout(function() {

    num =1;

}, 1000)

我这样测，发现，页面并没有渲染呀。希望老师抽空能解答一下，不胜感激！

2016年12月20日 11:41
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-370687)
 | [引用](#comment-text)

风一样的男人

 说：
                

redux大法看的好吃力

2016年12月28日 01:59
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-371188)
 | [引用](#comment-text)

Peter

 说：
                

乏味，且不明所以。感觉作者自己也不懂

2017年1月 2日 22:58
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-371472)
 | [引用](#comment-text)

Andy

 说：
                

感谢阮老师的付出，阮老师的博文总是清晰易懂。

阮老师为什么不在文章末尾放个支付宝或者微信的二维码呢？我想给阮老师买杯咖啡☕️ ~ 相信很多人也会有这想法的，毕竟我们从阮老师这里学到了很多~

2017年1月 7日 16:12
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-371703)
 | [引用](#comment-text)

qinicy

 说：
                

最近对React-Native大感兴趣，大概地撸了一遍阮老师的博客，虽然不是前端出身，但理解起来不难，好文章。

2017年1月13日 16:33
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-371988)
 | [引用](#comment-text)

高峰

 说：
                

第三章说了异步操作，可是你 react-redux 里面没有说，怎么异步操作啊。是参照第二章吗？我现在使用react-redux 请教，怎么选择异步fetch 返回数据啊。

2017年1月16日 12:05
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-372018)
 | [引用](#comment-text)

lilieming

 说：
                

如果你省略这个 mapDispatchToProps 参数，默认情况下，dispatch 会注入到你的组件props 中。

2017年1月19日 21:10
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-372130)
 | [引用](#comment-text)

nicemayi

 说：
                

请问阮老师， Counter例子中的createStore代码：

const store = createStore(

  todoApp,

  persistedState

);

是不是有问题？ createStore接受的第一个参数应该是reducer（本例中是counter）， 而不是UI组件。

2017年2月10日 03:46
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-372631)
 | [引用](#comment-text)

张凯

 说：
                

总觉得代码部分用粉红有点突兀，影响阅读，颜色是否可以弱化点

2017年2月18日 23:50
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-373123)
 | [引用](#comment-text)

[LeoEatle](http://istillhaveboobs.com)

 说：
                

>     引用nicemayi的发言：
> 
> 
> 请问阮老师， Counter例子中的createStore代码：
> 
> const store = createStore(
> 
> todoApp,
> 
> persistedState
> 
> );
> 
> 是不是有问题？ createStore接受的第一个参数应该是reducer（本例中是counter）， 而不是UI组件。

这里的createStore确实应该是传参数名错了

2017年2月20日 14:12
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-373153)
 | [引用](#comment-text)

张铮

 说：
                

虽然没太看懂，打算再看一遍 ，谢谢阮老师的良心教程

2017年2月22日 23:09
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-373300)
 | [引用](#comment-text)

sophie

 说：
                

const store = createStore(

todoApp,

persistedState

);

这里的确不是Counter的代码，源代码大家可以看阮老师的源代码，应该是这样的：

// Store

const store = createStore(counter);

2017年3月 1日 15:18
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-373687)
 | [引用](#comment-text)

黎龙

 说：
                

收益匪浅啊，感谢阮老师。

2017年3月 3日 17:50
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-373856)
 | [引用](#comment-text)

sakop

 说：
                

谈一下我阅读了阮老师三篇文章后的理解，很有可能是有偏差的，不足请指出，谢谢！

阮老师上文中关于Provider的解释，缺少了对context的介绍，我补充一下吧：

为了让子组件能够获得context属性，React强制要求根组件（此处为Provider组件）提供getChildContext实例方法，以及类属性childContextTypes。而子组件想要获取context，也必须定义类级别的Counter. contextTypes属性。定义是双向的，如果缺少了任何一块，子组件都获取不到context属性。

我认为父组件的那块定义是在Provider的代码中实现的，而子组件的那部分是在connect方法中实现的。

因此connect方法为Counter组件添加的context属性实质上是由Provider传下来的，这样在mapStatesToProps方法里的state参数实质上就是this.context.store.getState()方法获得的。

然后看一下页面首次加载以及之后有互动行为之后整个逻辑的流程：

当第一次渲染页面时，store里的初始state是怎么获得的呢？

代码一开始一般就是 

createStore(reducers,defaultParams)的调用，其中reducers可以使一个reducer，也可是redux.combineReducers过的reducer的集合。

createStore方法会对每个reducer去dispatch一个action.type=@@redux/INIT类型的action，而这个action一般在reducer的代码里不会被handle，直接掉入default块，于是就返回了state的初始状态。

然后一般就会ReactDom.render(将应用渲染出来，每个子组件的容器组件通过传入this.context.store.getState()方法获得的state对象, 以及容器组件上自带的ownProps给mapStatesToProperties方法，来构建props，最后将props应用到子组件的UI组件上。

当在子组件上发生交互行为，如click时，mapDispatchToProps会定义click触发时应该dispatch哪一个action的映射。

然后store接收到这个action后会进行reduce，得到最新的state，然后再调用所有的子组件的mapStatesToProps方法生成新的props。

最后对Provider进行重新渲染，当然上面的事件计算出来的很多state可能都不会发生变化，所以diff算法不会去修改这些没有发生变化的组件，因此性能也比较好。

2017年3月14日 16:02
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-374720)
 | [引用](#comment-text)

捕捉流星的孩子

 说：
                

疑问开头的UI和container的划分：

（UI只负责呈现，不包含业务逻辑；container只负责业务逻辑不包含UI呈现）

对于一个页面， 真的能划分只有UI和container两种组件吗？

假设一个页面对应一个container，我的情况是总会出现在页面级container下混合UI+其他container。。

求解。。

2017年3月14日 18:11
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-374725)
 | [引用](#comment-text)

阿范

 说：
                

请教大神或各位个问题，

在ui组件中，如果行为中需要传参该怎么做？

比如目前是 ;

但比如有多个button,需要sendClickAction时传递入参id，怎么做？

2017年3月16日 10:40
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-374886)
 | [引用](#comment-text)

前端小白白

 说：
                

三篇看下来有点累，什么时候歇好了再来看，一峰老师写得好！

2017年3月22日 21:08
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-375289)
 | [引用](#comment-text)

皖林

 说：
                

五的最后:

const mapDispatchToProps = {

  onClick: (filter) => {

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  };

}

onClick的返回值应该加上()。({type: xxx})

2017年3月31日 17:44
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-375749)
 | [引用](#comment-text)

finalljx

 说：
                

建议阮一峰老师增加子组件如何通过context 获取到store的样例，对新手有较大帮助，我是看了官网文档之后才知道方法.
[https://facebook.github.io/react/docs/context.html](https://facebook.github.io/react/docs/context.html)

2017年4月18日 15:31
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-376416)
 | [引用](#comment-text)

Woody

 说：
                

>     引用finalljx的发言：
> 
> 
> 建议阮一峰老师增加子组件如何通过context 获取到store的样例，对新手有较大帮助，我是看了官网文档之后才知道方法.
> [https://facebook.github.io/react/docs/context.html](https://facebook.github.io/react/docs/context.html)

貌似官方不建议使用context。

It is an experimental API and it is likely to break in future releases of React.

2017年4月21日 13:11
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-376493)
 | [引用](#comment-text)

[Ajaxyz](http://123.23.24.344)

 说：
                

阮大神讲的果然通俗易懂，解决了我多年的困惑！感谢老师

2017年5月11日 16:29
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-377061)
 | [引用](#comment-text)

weijie

 说：
                

然道就我一个人看不懂嘛....

2017年5月12日 10:43
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-377075)
 | [引用](#comment-text)

xujun

 说：
                

懵逼中。。。。继续第二遍

2017年5月17日 16:23
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-377237)
 | [引用](#comment-text)

Neil

 说：
                

const mapDispatchToProps = {

  onClick: (filter) => {

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  };

}

这个函数是不是应该写成

const mapDispatchToProps = {

  onClick: (filter) => ({

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  });

}

箭头函数直接返回对象的话要加上括号

2017年6月 6日 17:54
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-377721)
 | [引用](#comment-text)

a

 说：
                

    const { store } = this.context;

然而并不行

求ruan老师贴代码的时候保证可执行，免得误导人！

2017年6月12日 16:24
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-377896)
 | [引用](#comment-text)

cc

 说：
                

最近在学react，看了很多，就这篇最有效，讲的太到位了。尤其是redux底层的原理，简直不能更赞。

2017年6月27日 23:17
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-378243)
 | [引用](#comment-text)

花自飘凌水自流

 说：
                

好屌啊!看着阮大神的代码,长大的!

2017年6月28日 13:28
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-378264)
 | [引用](#comment-text)

suvllian

 说：
                

获益匪浅

2017年7月12日 13:48
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-378638)
 | [引用](#comment-text)

civil

 说：
                

>     引用a的发言：
> 
> 
> const { store } = this.context;
> 
> 然而并不行
> 
> 求ruan老师贴代码的时候保证可执行，免得误导人！

<Provider store={store}>

   <App />

</Provider>

App所有子组件无法获取到store，因为this.context空值，请大师指教

2017年7月27日 18:24
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-379022)
 | [引用](#comment-text)

林047

 说：
                

react 的props不是应该放一些不变的东西吗？那现在右container的state每次提供不同的数据，不是和react的props设计思想有出入吗

2017年9月 1日 11:12
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-379980)
 | [引用](#comment-text)

zyh

 说：
                

>     引用Andy的发言：
> 
> 
> 感谢阮老师的付出，阮老师的博文总是清晰易懂。
> 
> 阮老师为什么不在文章末尾放个支付宝或者微信的二维码呢？我想给阮老师买杯咖啡☕️ ~ 相信很多人也会有这想法的，毕竟我们从阮老师这里学到了很多~

你是托把

2017年9月 1日 17:13
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-379992)
 | [引用](#comment-text)

秋梦槿

 说：
                

有人能帮我看下我的这个问题吗

是不是reducers写的有问题，

这是效果 [https://amanzyw.github.io/react-redux/dist/](https://amanzyw.github.io/react-redux/dist/)[https://amanzyw.github.io/react-redux/dist/](https://amanzyw.github.io/react-redux/dist/)

项目地址在：https://github.com/amanzyw/react-redux/tree/gh-pages

2017年9月23日 10:05
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-380761)
 | [引用](#comment-text)

健健

 说：
                

似懂非懂，写个demo先

2017年10月18日 16:41
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-381416)
 | [引用](#comment-text)

webLion200

 说：
                

阮老师，在实例的第四行文字解释是不是写错了？

“接着，定义value到state的映射，以及onIncreaseClick到dispatch的映射。”

应该是 “定义state到value的映射”吧

2017年10月26日 20:02
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-381714)
 | [引用](#comment-text)

爱吃鱼的猫

 说：
                

讲解的非常细致，自己看文档很多东西走马观花，理解不透彻。做项目的时候容易出现问题，再看看阮老师的文档有种茅塞顿开的感觉。

2017年10月27日 19:08
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-381743)
 | [引用](#comment-text)

nick

 说：
                

阮老师 果然厉害 学习redux 好几天都在蒙圈中。看来后立马感觉豁然开朗。

2017年11月 7日 17:33
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-382106)
 | [引用](#comment-text)

[nanxiaobei](http://mrlee.me)

 说：
                

>     引用Neil的发言：
> 
> 
> const mapDispatchToProps = {
> 
> onClick: (filter) => {
> 
> type: 'SET_VISIBILITY_FILTER',
> 
> filter: filter
> 
> };
> 
> }
> 
> 这个函数是不是应该写成
> 
> const mapDispatchToProps = {
> 
> onClick: (filter) => ({
> 
> type: 'SET_VISIBILITY_FILTER',
> 
> filter: filter
> 
> });
> 
> }
> 
> 箭头函数直接返回对象的话要加上括号

这个代码放到 IDE 里就会提示 error，可能是阮老并不用 IDE ...

2017年11月16日 15:57
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-382394)
 | [引用](#comment-text)

银桑

 说：
                

const mapDispatchToProps = {

  onClick: (filter) => {

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  };

}

此处应该改为：

const mapDispatchToProps = ({

  onClick: (filter) => {

    type: 'SET_VISIBILITY_FILTER',

    filter: filter

  }

})

去掉一个；和加了括号返回对象

2017年11月17日 16:24
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-382426)
 | [引用](#comment-text)

龙森

 说：
                

现在看阮老师的博客学习新技术，都成必须课了。赞一个！

2017年11月23日 23:42
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-382675)
 | [引用](#comment-text)

小冶

 说：
                

第六节多处提到context、子组件用到的state是不是写错了，应是store?

2017年12月 9日 23:34
 | [#](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html#comment-383109)
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
#### 参考 ####

