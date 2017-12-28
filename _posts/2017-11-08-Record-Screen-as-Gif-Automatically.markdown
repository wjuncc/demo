---
layout: post
title:  "Record Screen as Gif Automatically"
date:   2017-11-08 17:11:12 +0800
categories:
tags: 
    - powershell

---

# Record Screen as Gif Automatically #

How to deal with html?
enum a bat of htmls and generate a list file(.txt)   
key is the title   
value is the relative path  

preparing:

1. open shareX.exe, set the keyword for `record screen on window as gif`, likes `Ctrl+shift+G`.

programming:

1. active the chrome window
2. put the chrome window as a top window.
3. press `Ctrl+shift+G` by `autoIt` or `AutoHotkey`, active the self-defined command of shareX
4. copy the text from system clipboard, because shareX set the url of gif to system clipboard after uploaded successful.   
5. done.

![](https://i.imgur.com/PisTEej.gif)

