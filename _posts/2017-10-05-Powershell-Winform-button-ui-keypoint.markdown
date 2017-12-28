---
layout: post
title:  "Powershell Winform button ui - keypoint"
date:   2017-10-05 21:16:06 +0800
categories:  
tags: 
    - powershell

---



### Error ###
no `Set` here:  
```powershell
Set-Variable : 无法将参数绑定到参数“Name”，因为该参数是空值。
+     Set $arr = python E:\n\wj\171207_blogAuto\v66_powershell\acp____\Build_power ...
```
Delete `Set` 


```powershell
addButton $Form $count $label {python $script} 
```

```powershell
addButton $Form $count $label {python "$script"} 

```

![](https://i.imgur.com/gBT8F6j.gif)

```
---------------------------
2
---------------------------
C:/Windows/winsxs/amd64_microsoft-windows-gpowershell-exe_31bf3856ad364e35_7.1.7601.16398_none_87d5361b437881fa/powershell_ise.exe E:/n/wj/171207_blogAuto/powershell/ex/ps_button.ps1
---------------------------
确定   
---------------------------

```

### IndexOf in Powershell ###

```powershell

    $d = $str.EndsWith(".py")
    if($d){
        #[System.Windows.Forms.MessageBox]::Show($str ,"1")
      python "$str"
    }else{
        #[System.Windows.Forms.MessageBox]::Show($str ,"2")
      "$str"
    }
```
wrong:

```powershell
a.  [string]$a.contains("m")

b.  $a.contains(“m”)

c.  [regex]::match($a,"m")

d.  ([regex]::match($a,"m")).success
```

* [PowerTip: Finding Letters in Strings with PowerShell – Hey, Scripting Guy! Blog](https://blogs.technet.microsoft.com/heyscriptingguy/2012/09/06/powertip-finding-letters-in-strings-with-powershell/)


### Running Powershell but Hidden the black window ###

Way1
`E:\n\wj\171207_blogAuto\powershell\ex\ps_button.vbs`
```vbs
CreateObject("WScript.Shell").Run "cmd /c E:\n\wj\171207_blogAuto\powershell\ex\ps_button.ps1",0
```
Way2 
`E:\n\wj\171207_blogAuto\powershell\ex\ps_button.bat`
```bat
@echo off
if "%1" == "h" goto begin 
mshta vbscript:createobject("wscript.shell").run("%~nx0 h",0)(window.close)&&exit 
:begin
cd E:\n\wj\171207_blogAuto\powershell\ex
ps_button.ps1
```
* [批处理隐藏自身窗口，很无聊_DOS/BAT_脚本之家](http://m.jb51.net/article/14352.htm)


### How do you pass function as a parameter in powershell ###


And in your new_btn function you probably just need to use
```
$object.add_Click($onClick)
```
If you really want to pass a string, then you probably need to use the following:
```
$object.add_Click({ & $onClick })
```

```
addButton : 无法将“addButton”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保路径正确，然后再
试一次。
```
$Font = New-Object System.Drawing.Font("",16,[System.Drawing.FontStyle]::Bold)
$Dialog.Font = $Font;


```
+         $arr = python $path
+                ~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (Python 2.7.10 (...ntel)] on win32:St 
   ring) [], RemoteException
    + FullyQualifiedErrorId : NativeCommandError
```