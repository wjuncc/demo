---
layout: post
title:  "React & JS Plan"
date:   2017-10-01 07:10:42 +0800
categories:  
tags: 
    - react

---

There are two simple ways to get the total javscript definition at once: one is the Java JDK in android default package, the other is the virtual file in Websotrm software. 

The old way which has been proved improperty, writing a web crawler to navigate the javascript doc site and extract the html page will become a swamp and bring you to the Abyss. The real difficult task is the data cleanning. Each webpages strcture is different from one another. The documents dont have a guaranty of having the full definition resolved.

Maybe markdown is good document structure, but i have never found any javascript document in markdown.

directory : 

E:\n\wj\workframe\android-20\org\w3c

CSS define

[search in w3c](https://github.com/search?p=2&q=org%3Aw3c+flex-direction&type=Code)
flex-direction
css-validator-testsuite/properties/positive/flex-direction/css3/001.css
E:\n\learn\css\css-validator-testsuite\properties\positive
C:\Program Files (x86)\91 Wireless\AppleAssist\
```ps
cd E:\n\learn\css
git clone https://github.com/w3c/css-validator-testsuite.git

```
[](https://www.w3.org/TR/css-flexbox-1/)

### one way to in webstorm: ###

`File` -> `Settings` -> `Languages&Frameworks` -> `Javascript` -> `Libraries`，  
在右侧找到Download，下拉选择 `TypeScript community stubs`，然后滚动找到`node`，点击`Download`即可。


abbrev	https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/abbrev/

node-7z	https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/node-7z/


![](https://i.imgur.com/OlpIffP.gif)  
copy the address form the `Edit Library` panel.
```
http_github.com_DefinitelyTyped_DefinitelyTyped_raw_master_types_node_index.d.ts	Debug
```
Replace underscore with slash:
```
https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/node/inspector.d.ts	Debug
```