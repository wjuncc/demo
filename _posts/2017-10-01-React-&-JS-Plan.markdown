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


one way to in webstorm:

File -> Settings -> Languages&Frameworks -> Javascript -> Libraries，在右侧找到Download，下拉选择TypeScript community stubs，然后滚动找到node，点击Download即可。

abbrev	https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/abbrev/

node-7z	https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/node-7z/


http_github.com_DefinitelyTyped_DefinitelyTyped_raw_master_types_node_index.d.ts	Debug

https://github.com/DefinitelyTyped/DefinitelyTyped/raw/master/types/node/inspector.d.ts	Debug