---
layout: post
title:  "动画与ReactTransitionGroup"
date:   2017-12-20 03:47:21 +0800
categories:  
tags: 
    - react
    - 笔记

---

### 何时以及如何使用ReactTransitionGroup ###

虽然几乎所有的动画都可以在CSS中完成，但一旦达到一定的复杂程度，往往会更难维护。

[ReactTransitionGroup](https://www.npmjs.com/package/react-addons-transition-group)是构建ReactCSSTransitionGroup的基础API。 
两者之间的主要区别在于，ReactTransitionGroup动画是用Javascript而不是CSS编写的，并且在动画完成时提供了一个回调，而不是依赖于CSS转换事件。

### 从简单开始 ###
先把动画放在一边。 我们从一个简单页面开始，这个页面只有一个div，这个div是显示在ShowBox标。
```javascript
import React from 'react';
import { render } from 'react-dom';

class Page extends React.Component {
  state = {
    shouldShowBox: true
  };

  toggleBox = () => {
    this.setState({
      shouldShowBox: !this.state.shouldShowBox
    });
  };

  render () {
    return <div className="page">

      { this.state.shouldShowBox && <div className="box"/>}

      <button
        className="toggle-btn"
        onClick={this.toggleBox}
      >
        toggle
      </button>
    </div>;
  }
}

render(<Page/>, document.querySelector('#container'));
```

当shouldShowBox为true时，.box是可见的，为false时，则不可见。

### 添加ReactTransitionGroup ###
安装[react-addons-transition-group](https://www.npmjs.com/package/react-addons-transition-group)
	

	npm install react-addons-transition-group

然后import到文件:

	import TransitionGroup from 'react-addons-transition-group';

现在，将TransitionGroup添加到“Page”组件的render()中，即:
```
// ...
  render () {
    return <div className="page">

      <TransitionGroup>
        { this.state.shouldShowBox && <div className="box"/>}
      </TransitionGroup>

      <button
        className="toggle-btn"
        onClick={this.toggleBox}
      >
        toggle
      </button>
    </div>;
  }
// ...
```

为了让TransitionGroup中的组件具有不同的动画的灵活性，TransitionGroup本身并没有定义动画，而是在添加或删除子组件时，调用相应的输入或在其子组件上留下动画钩子。

一般只会用到这两个生命周期的钩子 - 

* componentWillEnter(callback)

调用添加到现有TransitionGroup的组件，在组件componentDidMount的时候。 
没有调用整个TransitionGroup的初始渲染（例如，当一个页面被初始加载时），为了你要componentWillAppear

* componentWillLeave(callback) 

调用已经从TransitionGroup中删除的组件。
发生在componentWillUnmount之前，而且，只有执行了这里的回调，componentWillUnmount才会触发。
注意，必须在动画结束后调用所提供的回调函数，否则组件将进入但不能离开，或者能离开但不能进入。

有关动画生命周期钩子的详细信息，参阅[官方文档](https://reactjs.org/docs/animation.html#low-level-api-reacttransitiongroup)。

因为ReactTransitionGroup依赖于钩子，而div并没有定义它们，所以必须首先将 <div className=box/>移动到它自己的组件中:

	class Box extends React.Component {
	  render () {
	    return <div className="box"/>;
	  }
	}

然后添加动画生命周期的钩子中。这样一来，就可以使用GSAP TweenMax做动画了。

2017年6月23日-更新:现在使用refs来引用DOM元素。
参考[Refs and the DOM](https://reactjs.org/docs/refs-and-the-dom.html)  

对于那些不熟悉TweenMax的人来说，下面是函数signature的fromTo :

	TweenMax.fromTo( target : Object, duration : Number, fromVars : Object, toVars : Object ) : TweenMax 

下面是使用ReactTransitionGroup的简单动画案例！

接下来几个部分讲， 高级重用动画组件，路由器集成，协调嵌套转场动画。

你读了这么多，也喜欢调试Javascript的干货(quick and dirty skill)??，给我发tweet@CheapSteak :）

您可能还对react-transition-group-plus感兴趣，用来代替ReactTransitionGroup，可中断转场，并指定转场顺序。看[demo](http://cheapsteak.github.io/react-transition-group-plus/)。

Thanks to @hare_ben and @jephuff for proofreading and feedback
感谢@hare_ben和@jephuff的校对和反馈

注册我的newsletter，订阅邮箱新文章。
ReactJavaScriptAnimationNPM
One clap, two clap, three clap, forty?
一个拍手，两个拍手，三个拍手，四十个？
通过或多或少的鼓掌，您可以向我们表明哪些故事真正脱颖而出。
   
----------------------------------------

### 留言板 ### 

Chang Wang（作者）   
八月二十七日 

谢谢，设法得到它与一些tweeks工作。 
如果是用Node，安装gsap插件使用TweenMax功能。 
下面是我的代码:

```
import React from 'react';
import { TweenMax } from 'gsap';

export default class Box extends React.Component {

  componentWillEnter(callback) {
    const el = this.container;
    TweenMax.fromTo(el, 0.3, { y: 100, opacity: 0 }, { y: 0, opacity: 1, onComplete: callback });
  }

  componentWillLeave(callback) {
    const el = this.container;
    TweenMax.fromTo(el, 0.3, { y: 0, opacity: 1 }, { y: -100, opacity: 0, onComplete: callback });
  }

  render() {
	 return (
      <div className="box" ref={c => this.container = c} />
    );
  }
}
```

Box.jsx 
```
import React from 'react';
import { TransitionGroup } from 'react-transition-group';
import Box from './Box';

export default class Page extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      shouldShowBox: true,
    };
    this.toggleBox = this.toggleBox.bind(this);
  }

  toggleBox() {
    this.setState({
      shouldShowBox: !this.state.shouldShowBox,
    });
  }
  render() {
    return (
      <div className="page">
        <TransitionGroup>
          { this.state.shouldShowBox && <Box />}
        </TransitionGroup>
        <button className="toggle-btn" onClick={this.toggleBox}>toggle</button>
      </div>
    );
  }
}
```

Page.jsx
```
.page {
  height: 100%;
}

.box {
  width: 100px;
  height: 100px;
  background-color: #3498DB;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
}

.toggle-btn {
  position: absolute;
  top: 20px;
  right: 0;
  left: 0;
  margin: auto;
  width: 80px;
}
```
#### 3 ####
2016年5月21日  
这篇blog是讲React Animations的，我找了一天半才找到。
非常感谢。
讲的很清楚。
  
#### 4 ####
Amanda Koster  
阿曼达科斯特  
八月二十九日   
谢谢！ 
非常靠谱，我学到了Tweens！


#### 5 #### 
Joshua Ellis  
约书亚·埃利斯   
9月1日   
谢谢！ 
让我的动画最终跑起来。
这是[ReactTransitionGroup文档链接](https://github.com/reactjs/react-transition-group/tree/v1-stable),有谁会需要它

Also note the import to get it working is :
另外请注意，导入的写法是:

	import TransitionGroup from react-transition-group/TransitionGroup;

#### 9 ####
2016年3月16日   
试试react f1  
 
Mar 16, 2016  
2016年3月16日   
ReactTransitionGroup不依赖于this.props.style，而是直接操纵DOM react-f1也是一样），因此动画的性能不会被虚拟dom放慢）


Jeremy Marc  
杰里米·马克   
8月30日  
谢谢你的文章。
关于react，我有一个问题;
当组件可见时（例如阻止动画）如何启动动画。
什么是处理这个最好的方法？
谢谢！



8月30日
嗨，杰里米
取决于你想要的哪种动画。  
如果它是两个组件组成的动画，其中一个可见（例如淡入或滑入），另一个动画在其变为可见（例如执行旋转 spin）之后出现，那么我把这两个组件放在componentWillAppear / componentWillEnter中
sequence
序列

Jeremy Marc  
杰里米·马克  
八月三十一日  
那么，每个组件都必须包含react-transition-group对吗？
在这种情况下如何调用呢？
谢谢！

八月三十一日
对不起，我想我可能误解，要想解决问题，你最好先创建一个codepen/fiddle/sandbox？ 
: )

编辑:哦，我想我明白你的意思了。
如果组件只在显示时有动画，那么你可能不需要React Transition Group，试试在componentDidMount中触发动画

------------------------------------

Chang Wang和Sourabh Kumar的对话。
8月3日  

对于React动画。我找了有段时间了，而ReactTransitionGroup似乎很接近了的。

但是有一件事值得我注意。

我们通过生命周期钩子所做的动画，都对实际的DOM节点进行操作，而不是对虚拟DOM进行操作。

而且我们知道React并不知道render方法之外发生的变化。
这意味着React将无法解释我们的动画做出的变化和它的反应（双关）(pun unintended) ，就好像它们根本不存在一样。

你有什么想法？

------------------------------------

8月3日
感谢评论！

这当然要权衡一下。 
只要动画所操作的DOM属性，和组件state而更新的DOM属性，不重叠，这就不是问题。

但是，如果你的rander函数为某个元素指定特定的值，例如，基于一个变化的状态的transform属性，同时，这个状态在DOM属性被直接从生命周期钩子中的方法操作的同时改变，那么会有一些跳跃和怪异的行为。

由于RTG只适用于入口entrance和出口exit动画（当你的组件的内部状态不应该改变时），这应该很少会引发问题，但一定要记住？


------------------------------------
Sourabh Kumar  
Sourabh库马尔   
8月3日   
谢谢你抽出时间写回复，Chang！

我同意。 

这似乎是一个可以与之共存的折衷。 
相信我，我试过几乎所有可用的解决方案。 
到目前为止我已经试过:

ReactCSSTransitionGroup :仅基于RTG。
但它不是我的菜：介于CSS和JS之间的耦合。

React Motion :我真的很喜欢这个，但是当你试图构建复杂的顺序动画的时候，效果不好。
此外也没有卸载动画的API。

Velocity-React和React-GSAP-Enhancer :要给组件强加代理属性HOC。
这会干扰到组件的生命周期，事情会变得笨拙和丑陋。

我发现最后两个选择，直到我意识到，他们只适合用在延迟转场动画上，但对于大型复杂的动画，他们做不到（they just dont make the cut）。

然后我开始研究RTG，我喜欢它通过生命周期钩子提供的灵活性。

我可以使用我喜欢的工具，如GSAP，Velocity或Anime制作超级流畅的动画。

使用它，对于生产环境很有意义。

I used to shy away initially from using other JavaScript tools with React because of the whole virtual DOM flow, until recently when I realized that in order to get things function perfectly on a production scale, Ill have to adjust with certain trade offs.
因为整个虚拟DOM流程，我最初从使用React来避免使用其他JavaScript工具，直到最近当我意识到为了在生产规模上完美地实现功能时，我必须进行一些权衡调整。
At least till the time we figure out how to do all this through virtual DOM.
至少在这个时候，我们想通过虚拟DOM来做到这一点。 
??
??

----------------------------

shaggy
毛茸茸
2016年11月16日
This is really thought provoking, Im new to HOC stuff.
这真的是令人兴奋的，我新HOC的东西。
But can I ask why are you using Transition group at all , you could just tween the wrapped component using componentDidMount and componentWillUnmount lifecycle hooks ?
但是，我可以问为什么你使用Transition组，你可以使用componentDidMount和componentWillUnmount生命周期钩子补间包装的组件？
To be honest I had trouble getting your example to work but using the react lifecycle hooks above works OK??thanks for the
说实话，我有麻烦得到你的例子工作，但使用上面的反应生命周期钩作品OK ??谢谢你

Read more
阅读更多

1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Nov 17, 2016
2016年11月17日
Hi shaggy
你好毛茸茸

Are you sure the leave-animation in `componentWillUnmount` would run through?
你确定`componentWillUnmount`中的离开动画会穿过吗？
That lifecycle hook is called immediately before the component is removed from the DOM, I would assume itd immediately disappear.
该生命周期钩子在组件从DOM中移除之前被立即调用，我会认为它立即消失。

The two main benefits of using TransitionGroups lifecycle hooks is to be able to
使用TransitionGroups生命周期钩子的两个主要好处是能够

Read more
阅读更多


Conversation with Chang Wang.
与张望的对话。
Go to the profile of ffxsam
转到ffxsam的配置文件
ffxsam
ffxsam
Sep 25, 2016
2016年9月25日
Since use of findDOMNode is discouraged, is there a better way today for a React component to access its own DOM node?
由于不鼓励使用findDOMNode，现在有更好的方法让React组件访问它自己的DOM节点吗？


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Sep 26, 2016
2016年9月26日
You _could_ use refs if you prefer
如果你愿意，你可以使用参考


Read more
阅读更多

1
1

Conversation with Chang Wang.
与张望的对话。
Go to the profile of Andrew Leith
转到Andrew Leith的个人资料
Andrew Leith
安德鲁·利思
Nov 15, 2016
2016年11月15日
Hi Chang,
Hi Chang，

I was toying around with this concept and just ended up putting some animations on componentDiMount.
我正在玩这个概念，最后在componentDiMount上添加了一些动画。
Do you see an issue with this?
你看到这个问题吗？
The only obvious drawback I see is I cant animate on the way out
我看到的唯一明显的缺点是我不能在出路上进行动画制作


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Nov 17, 2016
2016年11月17日
Hi Andrew, if `componentDidMount` is sufficient for your needs (dont need to animate out, dont need to separate appears with enters) then its perfectly fine to use just that  : )
嗨安德鲁，如果`componentDidMount`足够您的需要（不需要动画了，不需要单独出现与进入）那么它完全正确地使用只是:）


1 response
1回应
Go to the profile of Andrew Leith
转到Andrew Leith的个人资料
Andrew Leith
安德鲁·利思
Nov 23, 2016
2016年11月23日
Thank you Chang.
谢谢张
Another question, if you dont mind.
另一个问题，如果你不介意。
A lot of resources (eslint being the most in my face) are telling me not to use `findDOMNode` but instead to use refs.
很多资源（eslint是我脸上的最多）告诉我不要使用findDOMNode而是使用refs。
This makes everything very messy as I need to explicitly put references to bits of markup so I can animate them.
这使得一切都非常混乱，因为我需要明确地把引用标记的位，所以我可以动画他们。

Do you have any point of view on this?
你有什么观点吗？


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Nov 25, 2016
2016年11月25日
Thats a good question
这是个好问题

Reading through the discussion on the issue that introduced the rule, specifically the points brought up by jquense and taion, there are situations where using findDOMNode is currently unavoidable (eg animations in a HOC), at least until a standardized way to reliably pass refs down
通过讨论引入规则的问题，特别是由jquense和taion提出的问题，有些情况下，使用findDOMNode目前是不可避免的（例如HOC中的动画），至少直到标准化的方式可靠地通过ref
through wrapped
通过包裹

Read more
阅读更多


Conversation with Chang Wang.
与张望的对话。
Go to the profile of Jeanmichel Cote
转到Jeanmichel Cote的个人资料
Jeanmichel Cote
Jeanmichel Cote
Oct 12, 2016
2016年10月12日
Well, I managed to find a way to make it work using Promises.
那么，我设法找到一种使用Promise工作的方法。
You basically wrap your TimelineLite.staggerFrom` call in a promise.
你基本上包装你的TimelineLite.staggerFrom`调用的承诺。
When the promise is resolved, you call TimelineLite.eventCallback("onComplete", callback)`.
当承诺解决后，您可以调用TimelineLite.eventCallback（“onComplete”，callback）`。

So as you see, I do pass the callback from the componentWillEnter` and compononentWillLeave` hooks, but
所以如你所见，我确实通过了componentWillEnter和componentWillLeave钩子的回调，

Read more
阅读更多

1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Oct 15, 2016
2016年10月15日
Hi Jeanmichel!
嗨，让米歇尔！


You could also use gsap-promise
你也可以使用gsap-promise

gsap-promise
GSAP-承诺

a Promise wrapper around gsap / tweenlite
gsap / tweenlite的Promise包装器
www.npmjs.com
www.npmjs.com

var animate = require('gsap-promise')
var animate = require（'gsap-promise'）
//..
// ..
componentWillLeave(callback) {
componentWillLeave（callback）{
animate.staggerFromTo(...).then(callback)
animate.staggerFromTo（...），然后（回调）
}
}

#### 参考 ####

* [Animations with ReactTransitionGroup – Appify – Medium](https://medium.com/appifycanada/animations-with-reacttransitiongroup-4972ad7da286)
* [动画 - React](https://react-cn.github.io/react/docs/animation.html)
* [React 动画 - ZhusCafe](http://zhuscat.com/2016/08/31/react-animation/)
* [使用ReactTransitionGroup实现React动画效果 · Issue #3 · luckyhalley/blog · GitHub](https://github.com/luckyhalley/blog/issues/3)
* [交互动画系列之三：react动画 · Issue #57 · youngwind/blog · GitHub](https://github.com/youngwind/blog/issues/57)
* [ReactTransitionGroup动画原理 - Web前端 腾讯IVWeb 团队社区](https://ivweb.io/topic/586099050e2a26d26bb1c029)
* [React动画实践 - AlloyTeam](http://www.alloyteam.com/2016/01/react-animation-practice/)
* [动画 · React入门指南 · 看云](https://www.kancloud.cn/kancloud/react-quickstart/44617)
* [React学习之扩展动画（三十）--CSS,ps,DOM,Group,ReactCSSTransitionGroup,组件,动画,ReactTransitionGroup](http://www.bijishequ.com/detail/395468?p=70)