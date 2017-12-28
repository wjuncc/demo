---
layout: post
title:  "Markdown Tool Sets - Intro"
date:   2017-10-05 20:16:06 +0800
categories:  
tags: 
    - powershell

---

### Feature ###

* A tool sets of markdown files to speed up the editing of markdown files.
* Also a simple  demo to call python file in powershell
* data defined in json file.
* Dependent on software `MarkdownPad`, `Listary`


### Usage ###
1. set hotkey `wj2`(or keyword else you like) in software `Listary`, set the `URL` as `E:\n\wj\171207_blogAuto\powershell\ex\ps_button.vbs`

	![](https://i.imgur.com/mJsFgke.gif)

2. edit `vbs` below:
	
	```vbs
	CreateObject("WScript.Shell").Run "cmd /c E:\n\wj\171207_blogAuto\powershell\ex\ps_button.ps1",0
	```

3. double click `Ctrl` to active `Listary`, and input `wj2`, press `enter` key

	![](https://i.imgur.com/cqOFdIS.gif)

4. json file below:  
![](https://i.imgur.com/WJSQxVc.png)
### Effect ###
#### button2 - Create Markdown After Click Tags   ####
Create Markdown After Click Tags in Chrome automatically, and open it in software `MarkdownPad`  
![](https://i.imgur.com/3WIs0Kh.gif)


#### button3 - Create Markdown After Copy Words ####
Created a markdown file titled the words from the system clipboard you has just copied. And open it in software `MarkdownPad` also.  
![](https://i.imgur.com/hDhc8pm.gif)


#### button4 - Split the Markdown ####

Split the Markdown file to 2 separate ones. 
![](https://i.imgur.com/2all2TW.gif)

#### button5: Keep The Same Name with jeklly Tags ####
Keep The Same Name with jeklly Tags, if you modify the tags of title or date.
![](https://i.imgur.com/cW0g3kA.gif)


