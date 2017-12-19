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


The next few parts will be on reusing animations via higher-order components, integrating with react-router, and coordinating nested transitions.
接下来的几个部分将通过高级组件重用动画，与反应路由器集成，并协调嵌套转换。

If you've read this far then you might also like Quick and dirty tricks for debugging Javascript ??, and tweet at me @CheapSteak : )
如果你已经阅读了这么多，那么你可能也喜欢用于调试Javascript的快速和肮脏的技巧??，并发微博在我@CheapSteak :）

You may also be interested in react-transition-group-plus, a drop-in replacement for ReactTransitionGroup that allows interruptible transitions and specifying transition order.
您可能还对react-transition-group-plus感兴趣，ReactTransitionGroup允许可中断的转换并指定转换顺序。
See a comparative demo here.
在这里看到一个比较演示。

Thanks to @hare_ben and @jephuff for proofreading and feedback
感谢@hare_ben和@jephuff的校对和反馈

Sign up for my newsletter to receive new articles in your inbox.
注册我的通讯，在您的收件箱中收到新的文章。
ReactJavaScriptAnimationNPM
ReactJavaScriptAnimationNPM
One clap, two clap, three clap, forty?
一个拍手，两个拍手，三个拍手，四十个？
By clapping more or less, you can signal to us which stories really stand out.
通过或多或少的鼓掌，您可以向我们表明哪些故事真正脱颖而出。


340
340
12
12
Follow
跟随
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Pragmatic Perfectionist ?
务实的完美主义者？ 
Frontend Architect at OICR ?
OICR的前端架构师？ 
Director of Business Solutions at Appify
Appify商业解决方案总监

Follow
跟随
Appify
Appify
Appify
Appify
Tech articles and tutorials
技术文章和教程

More from Chang Wang
更多来自昌王
You dont need to know Dependency Injection
你不需要知道依赖注入
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王

849
849

Related reads
相关阅读
The next big industry to face digital disruption will be our nations
面对数字中断的下一个大行业将是我们的国家
Go to the profile of Kaspar Korjus
转到Kaspar Korjus的个人资料
Kaspar Korjus
卡斯帕Korjus

1.2K
1.2K

Responses
回应
Write a response
写一个答复
Applause from Chang Wang (author)
张望掌声（作者）
Go to the profile of Sjors van Heuveln
转到Sjors van Heuveln的个人资料
Sjors van Heuveln
Sjors van Heuveln
Aug 27
八月二十七日
Thanks, managed to get it working with some tweeks.
谢谢，设法得到它与一些tweeks工作。
For people working with Node, install the gsap package for use of TweenMax function.
对于使用Node的人员，安装gsap软件包以使用TweenMax功能。

Heres my version of the code :
下面是我的代码版本:

Read more
阅读更多

30
三十

Applause from Chang Wang (author)
张望掌声（作者）
Go to the profile of Spencer Carnage
转到斯宾塞大屠杀的配置文件
Spencer Carnage
斯宾塞大屠杀
May 21, 2016
2016年5月21日
The blog post about React Animations that I have been searching a day and a half for.
关于React Animations的博客文章，我一直在寻找一天半。
Thank you so much.
非常感谢。
This really clears things up.
这真的清除了事情。


9
9

Applause from Chang Wang (author)
张望掌声（作者）
Go to the profile of Amanda Koster
转到阿曼达科斯特的个人资料
Amanda Koster
阿曼达科斯特
Aug 29
八月二十九日
Thank you!
谢谢！
This totally worked and I learned about Tweens!
这完全奏效，我学到了Tweens！


5
五

Applause from Chang Wang (author)
张望掌声（作者）
Go to the profile of Joshua Ellis
转到Joshua Ellis的个人资料
Joshua Ellis
约书亚·埃利斯
Sep 1
9月1日
THANK YOU!
谢谢！
Finally got my animation running.
最后让我的动画运行。
Here is a link to ReactTransitionGroup docs for those of you who need it (like me) :  here
这里是一个链接到ReactTransitionGroup文档的人谁需要它（像我）:在这里

Also note the import to get it working is :
另外请注意，导入工作是:

import TransitionGroup from react-transition-group/TransitionGroup;
从react-transition-group / TransitionGroup导入TransitionGroup;

9
9

Conversation with Chang Wang.
与张望的对话。
Go to the profile of Ae
转到Ae的个人资料
Ae
阂
Mar 16, 2016
2016年3月16日

Try React F1
尝试反应F1


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Mar 16, 2016
2016年3月16日
ReactTransitionGroup does not rely on this.props.style but rather directly manipulates the DOM react-f1 does the same), hence the animation performance is not slowed down by virtualdom  : )
ReactTransitionGroup不依赖于this.props.style，而是直接操纵DOM react-f1），因此动画的性能不会被虚拟的_ __放慢）


1
1

Conversation with Chang Wang.
与张望的对话。
Go to the profile of Jeremy Marc
转到Jeremy Marc的个人资料
Jeremy Marc
杰里米·马克
Aug 30
8月30日
Hey Chang, thank you for your article.
嘿张，谢谢你的文章。
I have a question regarding react ;
我有一个关于反应的问题;
what if you want your animation to start when the component is visible (block animation for example).
如果您希望在组件可见时启动动画（例如阻止动画）。
Whats the best way to handle that?
什么是处理这个最好的方法？
Thanks!
谢谢！


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Aug 30
8月30日
Hi Jeremy.
嗨，杰里米
Depends on the kind of animation you have in mind.
取决于你想要的那种动画。
If its a 2-part animation??one where the component becomes visible (eg fade or slide in), the other where some animation occurs after it becomes visible (eg performs a spin) then I would put both inside the componentWillAppear/componentWillEnter in
如果它是一个由两部分组成的动画，一个组件变得可见（例如淡入或滑入），另一个动画在其变为可见（例如执行旋转）之后出现，那么我将把这两个组件放在componentWillAppear / componentWillEnter中
sequence
序列


1
1
1 response
1回应
Go to the profile of Jeremy Marc
转到Jeremy Marc的个人资料
Jeremy Marc
杰里米·马克
Aug 31
八月三十一日
So, each component has to be wrapped with react-transition-group right?
那么，每个组件都必须包含react-transition-group对吗？
What about performances in this case?
在这种情况下表演呢？
Thanks!
谢谢！


1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Aug 31
八月三十一日
Im sorry I think I might have misunderstood, having trouble visualizing the problem, would you mind creating a codepen/fiddle/sandbox?
对不起，我想我可能会误解，难以想象的问题，你会介意创建一个codepen /小提琴/沙箱？ 
: )
:）

edit :  Oh I think I know what you mean now.
编辑:哦，我想我知道你的意思了。
If the component only animates on appearing then you might not need React Transition Group, try triggering the animation in componentDidMount
如果组件只在显示时动画，那么你可能不需要React Transition Group，尝试在componentDidMount中触发动画


10
10
1 response
1回应
Conversation between Chang Wang and Sourabh Kumar.
Chang Wang和Sourabh Kumar的对话。
Go to the profile of Sourabh Kumar
转到Sourabh Kumar的个人资料
Sourabh Kumar
Sourabh库马尔
Aug 3
8月3日
Hi Chang Wang ,
您好张泓，

Great post first of all!
伟大的职位首先！
I myself have been exploring different ways to do animations in React for sometime now and ReactTransitionGroup seems to have come quite close to what Im looking for.
我自己一直在探索不同的方法来动画React一段时间，而ReactTransitionGroup似乎已经非常接近我所寻找的。

But theres one thing that concerns me.
但是有一件事关注我。
The animations that we do through the lifecycle
我们在整个生命周期中所做的动画

Read more
阅读更多

1 response
1回应
Go to the profile of Chang Wang
转到长王的档案
Chang Wang
常王
Aug 3
8月3日
Hi Sourabh,
嗨Sourabh，

Thanks for the comment!
感谢您的评论！

Theres certainly a tradeoff here.
这里当然是一个权衡。
As long as the DOM attributes youre manipulating dont overlap with DOM attributes that would be updated due to component state changes, this isnt a concern.
只要您操作的DOM属性不会与由于组件状态更改而更新的DOM属性重叠，这不是一个问题。

Read more
阅读更多

1 response
1回应
Go to the profile of Sourabh Kumar
转到Sourabh Kumar的个人资料
Sourabh Kumar
Sourabh库马尔
Aug 3
8月3日
Thanks for taking out time and writing back, Chang!
谢谢你抽出时间写回来，张！

I agree with you.
我赞同你。
This seems to be a trade off that one can live with.
这似乎是一个可以与之共存的折衷。
And trust me, Im saying that after trying out almost every solution thats available out there.
相信我，我试过几乎所有可用的解决方案。
So far Ive tried :
到目前为止我已经试过:

Read more
阅读更多

1
1

Conversation with Chang Wang.
与张望的对话。
Go to the profile of shaggy
转到毛茸茸的个人资料
shaggy
毛茸茸
Nov 16, 2016
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