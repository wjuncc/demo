---
layout: post
title:  "使用高阶组件重用ReactTransitionGroup动画"
date:   2017-12-20 03:45:26 +0800
categories:  
tags: 
---

# 使用高阶组件重用ReactTransitionGroup动画 #

Reusing ReactTransitionGroup animations with Higher-order Components
使用高阶组件重用ReactTransitionGroup动画
In my previous post we went over how to make a simple box animate when it enters and leaves a TransitionGroup.
在我之前的文章中，我们介绍了如何在进入和离开一个TransitionGroup时使一个简单的盒子变成动画。

If you recall, to give components inside the TransitionGroup flexibility to have differing animations, the TransitionGroup does not define animations itself, but will call the corresponding enter or leave animation hooks on its child components when they are added or removed.
如果您还记得，为了给TransitionGroup内部的组件提供灵活性，使其具有不同的动画，TransitionGroup本身并不定义动画，但会在添加或删除子组件时调用相应的输入或将子动画组件的动画挂钩。

But there are often times when we do want several components to share the same animation, preferably without duplicating code.
但是有时候我们经常需要几个组件共享相同的动画，最好不要复制代码。
That can be achieved using Higher-order Components (HOC).
这可以通过使用高阶分量（HOC）来实现。 
(If not already familiar with HOCs, heres a good intro)
（如果不熟悉HOC，继承人是一个很好的介绍）

Extracting the animations
提取动画
Lets take another look at the Box component from our previous exercise
让我们再看看我们之前练习中的Box组件


We can extract the parts specific to animation into a higher-order component called `fadesUp`
我们可以将特定于动画的部分提取到名为“fadesUp”的高阶组件中


Any component that wishes to have that animation behavior can be passed into `fadesUp` and enhanced.
任何希望具有该动画行为的组件都可以被传递到`fadesUp`并被增强。

Heres what that would look like for our Box
下面是我们的盒子的样子


Or, if you have decorators enabled (see Using ES7 Decorators with Babel 6)
或者，如果您启用了装饰器（请参阅使用Babel 6使用ES7装饰器）


Lets make a circle and give it the same animation
让一个圆圈，并给它相同的动画


Simple right?
简单的权利？

Passing Options
通过选项
Say we want to have animations take 0.3 seconds by default, but set the duration for Boxs animations take 0.8s.
假设我们希望动画默认需要0.3秒，但是将动画的持续时间设置为0.8秒。

This is what we want to be able to do :
这是我们希望能够做到的


Well have to modify our previous `fadesUp` to receive optional `options`, but due to the way that decorators work, its not quite as easy as adding an optional second parameter.
那么必须修改我们以前的`fadesUp`来接收可选的`options`，但由于装饰器的工作方式，它不像添加可选的第二个参数那么简单。

Heres how well have to modify the `fadesUp` HOC :
如何修改`fadesUp` HOC :


`fadesUp` now checks to see whether the type of the first argument received is a `function`, which would be when no options were passed and we assume we received a React class (es6 classes have typeof === function), so we
`fadesUp`现在检查收到的第一个参数的类型是否是一个`function`，当没有选项被传递时，我们假设我们收到了一个React类（es6类有typeof ===函数），所以我们
immediately enhance it.
马上加强吧。
If it did not receive a function, it assumes it received `options`, and returns a partially applied function that when next invoked will enhance the component passed to invoke it using the previously received `options`.
如果它没有收到一个函数，它会假定它收到了`options`，并且返回一个部分应用的函数，当下一次被调用时将会增强传递的组件以使用之前接收到的`options`来调用它。

It might be easier to understand why `fadesUp` had to be written the way it was after seeing how the HOC would be used without ES7 decorators :
可能更容易理解为什么`fadesUp`必须按照看到如何在没有ES7装饰器的情况下使用HOC的方式来书写:


Heres what it looks like put together :
下面是什么看起来放在一起:


You could take this even further and pass all the animation options as part of the options.
您可以更进一步，并通过所有动画选项作为选项的一部分。


The next parts will be on integrating with react-router and coordinating nested animations.
接下来的部分将集成反应路由器和协调嵌套动画。

More on Higher-order Components :
更多关于高阶元件:
Structuring React Applications :  Higher-Order Components
构建React应用程序:高阶组件

Follow Chang Wang on Twitter
在Twitter上关注Chang Wang

#### 参考 ####

* [React高阶组件（译） - 腾讯Web前端 IMWeb 团队社区 - blog - 团队博客](http://imweb.io/topic/5907038a2739bbed32f60dad)
* [React文档阅读--ps,DOM,js,HTML,组件,我们,props,使用,可以](http://www.bijishequ.com/detail/262287?p=70)
* [React - 高阶组件（Higher-Order Components） · Issue #52 · tcatche/tcatche.github.io · GitHub](https://github.com/tcatche/tcatche.github.io/issues/52)