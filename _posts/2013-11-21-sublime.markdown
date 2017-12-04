---
layout: post
title:  "[sublimeText3] sublimeText必备插件"
date:   2013-11-21 01:17:32 +0800
categories: jekyll update
---

## 必备插件 ##

## 24.1 Emmet ##

Emmet，写HTML/CSS必备。   

## 24.2 Autofilename ##

输入路径/图像/样式表/ JavaScript，提示下一个文件夹或文件名。    
安装Autofilename， 输入时看到文件夹，文件列表，以及图像宽度/高度。

## 24.3 HTML * CSS * JSON Prettify ##

漂亮的JSON和HTML-CSS-JS Prettify，将采取凌乱/格式错误的HTML，CSS或JSON格式和缩进它正确。
非常方便，当你收到一个生成的代码/ json需要可读的一个blob。

## 24.4 SidebarEnhancements ##

Sublime Text的侧边栏API在功能缺乏，对于依赖GUI编辑器的用户来说，这是个负担：只有右键单击才能发生。

	untitled.js

	重命名...
	删除文件
	在Finder中显示

Lackluster默认侧边栏  
SidebarEnhancements 给侧边栏增加了大量新功能。

### 打开用... ###

先从边栏中的其他程序中打开文件。
右键单击并打开/ Run 将打开该文件类型的操作系统的默认程序中的文件。

如果是HTML文件，将在默认浏览器打开。

对我来说，在Chrome Canary中打开HTML文件。

如果想从侧边栏打开FireFox呢？

我们需要添加另一个程序。

右键单击该文件，打开 - 编辑应用程序...。

打开一个sublime菜单JS0N文件。

继续并复制当前的一个应用程序，填写FireFox的相关信息。
这里改变的两个重要的行是niDn和“application11”。如果您以前安装了AutoFileName扩展名，应用程序路径将很容易填写。
 
Autofilename扩展名识别路径并建议应用程序
该扩展行将限制此应用程序某些文件类型。  
这是有道理的，我们只想打开.html和 htm文件，因此我们使用“extensions11：Irhtmi ihtmfl。将其保留为空（”extensions“：n•'）将显示包括文件夹在内的所有内容，也可以使用通配符，例如”extensionsn _... n *   
任何带有扩展名的文件。

一旦所有的说法和完成，我们已经成功地将Firefox添加到我们的边栏“打开方式”使用下面的代码片段:


	//  Open with  Firefox 
	{
	"caption":  "Firefox",
	"id" :  "side-bar-files-open-with-firefox",
	"command":  "side_bar_files_open_with",
	"args":  {
		"paths":[],
		"application":  "/Applications/Firefox.app",
		"extensions":"html|htm"
		"open_automaticallyr,  :  false  //  will  close  the view/tab  and launch the  application
	},



 
如果您在Windows或Linux上，请确保您使用适当的路径到您的程序。

想要所有这些？

使用以下片段将所有浏览器添加到您的侧边栏:

	//  Open with Firefox 
	{
	"caption":  "Firefox",
	"id":  "side-bar-files-open-with-firefox",
	"command":  "si de_bar_ f i1e s_open_wi th",
	"args":  {
	"paths” ： [],
	"application":  "/Applications/Firefox.app",
	"extensions":"html|htm"
	nopen_automatically"  :  false  //  will  close  the view/tab and launch the  application
	//  Open with Safari 
	{
	"caption":  "Safari",
	"id":  "side-bar-files-open-with-safari",
	"command":  "side_bar_files_open_with",
	"args，，：   {
	" p a t h s " : [],   
	"application" :  "/Applications/Safari.app",
	"extensions":"html|htm"
	"open一automatically"  :  false  // will  close  the view/tab and launch the  application
	//  Open with Chrome  Stable 
	{
	"caption":  "Chrome  Stable",
	"id":  "side-bar-files-open-with-chrome-stable",

	"command":  "si de_bar_ f i1e s_open_w i th",
	"args'1:  {
	"paths":[],
	"application":  "/Applications/Google  Chrome.app",
	"extensions":"html|htm"
	nopen_automatically”  :  false  //  will  close  the view/tab and launch the  application
	//  Open with Chrome Canary
	{
	"caption":  "Chrome  Canary",
	"id":  "side-bar-files-open-with-chrome-canary",
	"command":  "side_bar_files_open_with",
	"args":  {
	" p a t h s " : [],
	"application":  "/Applications/Google  Google  Chrome  Canary.app", 
	"extensions":"html|htm"
	"open一automatically"  :  false  // will  close  the view/tab and launch the  application
	//  Open with Opera
	{ 
		"caption":  "Opera",
		"id":  "side-bar-files-open-with-opera",
		"command" : "side_bar_f iles_cpen_TATith",
		"args":  {
		"paths":[],
		"application":  "/Applications/Opera•app",
		"extensions":"html|htm"
		},
		"open_automaticallyM  :  false  //  will  close  the view/tab  and launch the  application
	}


### 更多功能 ###

这些是相当直接的，不需要太多的解释，通过侧边栏剪切/复制/粘贴，Sublime没有默认的东西。
  
除了复制文件，复制路径，复制文件，复制为base64，粘贴父项和一些边缘情况

## 24.5 JSHint Gutter ##

JSHint Gutter 是Sublime Linter的另一种选择，如果你只需要JavaScript脚本。  
它可以更容易安装，并提供活的支撑，当出现瑕疵时将标记放置在排水沟中。      


## 24.6 Aligment ##

一些编码风格指南要求以某种方式对齐文本行。 

其中一个可能是让你=做变量声明时对齐。
有了这个包，我们可以把代码看起来像这个:

突出显示所有内容，然后点击^ + Ctrl + a
（在Windows上按Alt + Ctrl + a），使这个:


## 24.7  Bracket Highlighter ##

Bracket Highlighter 非常直观，帮你看到括号和标签开始/停止: 
 	
	
多行
 
匹配所有类型的括号


获取有颜色的括号要求您安装支持它的主题。 ","Getting colored brackets requires that you install a theme that supports it.",null,null,3],["Cobalt2准备好了。
195的202
 Sublime Text 高级用户

## 24.8 用SublimeText 写 Markdown ##

Markdown 是目前最好的写作方式。  
从项目的自述文件到博客文章到大型文档（如本书）的所有内容都可以用降价编写。
使用您的代码编辑器作为写作工具远胜其他工具，如Word或Google文档。  
也就是说，Sublime需要一些软件包，然后才能充分利用它作为文档编写者。

### 语法高亮 ###
 Sublime Text 有相当不错的语法高亮，所以没有任何包你已经设置开始写Markdown。

MarkdownEditing 包提供了一整套工具，包括两个高级主题，自动配对的markdown语法，如^下划线_和^星号*，以及一些键盘快捷键。
编译
虽然我建议使用Sublime Text编辑，而另一个程序（如Marked或Mau）编译您的Markdown，但如果您希望从Sublime Text进行编译，则可以使用这些选项。 

Markdown Preview可以让你编译成HTML格式，甚至可以在浏览器中用一个键盘快捷键预览它。


### 目录 ###

MarkdownTOC是一个将为您的整个文档生成目录的软件包。

只需运行命令MarkdownToc：insert toc一次你想要的目录，它会在每次保存时更新目录。

\u003c！ -  MarkdownTOC深度 - \u003e
 -  [企业]（＃约）
一（成长）（＃成长） - 工作 - 接触
\u003c！ -  / MarkdownTOC  - \u003e
＃关于[讲述]
 长大成长我在加拿大长大
＃工作
＃\t联系
一旦评论在您的代码中，您就有能力指定TOC深入多少标题级别。
默认情况下，目录不会被链接到标题，这是相当烦人的，但你可以通过给每个标题一个ID来补救。 ","By default, the TOC won't be linked to the title, which is rather annoying, but you can remedy that by giving each title an ID.",null,null,3],["MarkdownTOC会注意到这个ID并自动链接它们。
##成长[成长]
我必须告诫说，更新大文档的TOC可能会相当缓慢，而且在编辑器生成时似乎会阻止它。
197的202
 Sublime Text 高级用户

## 24.9 BufferScroll 保持文件状态 ##

大型文档中，代码折叠是不使用代码时隐藏大量代码的好方法。   
Sublime Text代码折叠的问题是折叠不会持续。  
重启Sublime Text，所有代码折叠都消失了！   
 
BufferScroll 插件，关闭文件时记住整个事情，包括:

* 滚动位置
* 光标位置
* 选择
* 分数
* 书签
* 代码折叠
* 选定语法
* 配色方案

## 24.10 Expand to quotes ##

这个包在前面的跳转，选择和移动部分被引用。 
崇高已扩大选择[行，单词，段落，范围，括号，缩进]，但没有“扩大到quotes”。

安装Expand to quotes。 
使用字符串或HTML属性时很有用。  

https_... //github.com/kek/sublime-expand-selection-to-quotes


## 24.11 TODO ##

将收集所有对TODO评论的引用，并编译到一个可链接的屏幕中。
https _... //github.com/robcowie/SublimeTODO

