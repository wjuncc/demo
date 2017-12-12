---
layout: post
title:  "powershell创建winForm"
date:   2017-12-08 20:25:46 +0800
categories:  
tags: powershell
---

# powershell创建winForm #

所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:239 字符: 1
+ FNloaddata
+ ~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (FNloaddata:String) [], CommandNotFoundExcept 
   ion
    + FullyQualifiedErrorId : CommandNotFoundException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
 
New-Object : 找到“ListViewItem”的多个不确定重载，参数计数为:“2”。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:206 字符: 25
+         $ListViewItem = New-Object System.Windows.Forms.ListViewItem($infoLine,  ...
+                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [New-Object]，MethodException
    + FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Command 
   s.NewObjectCommand
 
使用“1”个参数调用“AddRange”时发生异常:“值不能为 null。
参数名: items”
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:207 字符: 9
+         $ListView.Items.AddRange($ListViewItem)
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 


  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
    + FullyQualifiedErrorId : ArgumentNullException
 
索引操作失败；数组索引的计算结果为 Null。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:204 字符: 9
+         $infoOne = $arr[$line];
+         ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException
    + FullyQualifiedErrorId : NullArrayIndex
 
不能对 Null 值表达式调用方法。
所在位置 E:\n\wj\171212_En_Pdf_Trans\v66\ps1\ultimate.ps1:205 字符: 9
+         $infoLine =  $infoOne.split(",");
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) []，RuntimeException




[svg](http://www.sarasoueidan.com/blog/svgo-tools/)

[w3cplus](https://www.w3cplus.com/svg/svg-tips-for-designers.html)





[PowerShell 在线图形设计器，可以快速地创建代码](http://www.poshgui.com/) 





git搜索：Csv  GridView example  language:PowerShell

### 测试1 ###
测试：https://github.com/mpearon/PowerShell/blob/e5a1882fb8a49acedd5015f3f06f1872a9fda9e7/Personal/ScratchPad/Select-FromGridView.ps1

报错：

	PS C:\Users\Administrator> E:\n\wj\171207_blogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f06f1872a9fda9e7\Personal\ScratchPad\Select-FromGridView.ps1
	无法加载文件 E:\n\wj\171207_blogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f0
	6f1872a9fda9e7\Personal\ScratchPad\Select-FromGridView.ps1。文件 E:\n\wj\171207_bl
	ogAuto\powershell\PowerShell-e5a1882fb8a49acedd5015f3f06f1872a9fda9e7\Personal\
	ScratchPad\Select-FromGridView.ps1 未进行数字签名。不会在系统上执行该脚本。有关详细信息，请参阅 http://go.mic
	rosoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
	    + CategoryInfo          : SecurityError: (:) []，ParentContainsErrorRecordE 
	   xception
	    + FullyQualifiedErrorId : UnauthorizedAccess
	
	PS C:\Users\Administrator> 


在PowerShell执行以下输入： 

查看当前策略：

	Get-ExecutionPolicy

返回

	PS C:\Users\Administrator> Get-ExecutionPolicy 
	RemoteSigned

修改当前策略：

	set-ExecutionPolicy Unrestricted
	回车

listary 快捷键：ISE

 
### 测试2 ###
https://github.com/masters274/Posh_Repo/tree/8ae45da25bc425b18aff1924ac7396a3d34cdee8


#### 参考 ####

* 在线ui
* [PowerShell 技能连载 - 在 PowerShell 中创建 WinForms GUI 界面 - 叹为观止](http://blog.vichamp.com/2016/12/23/creating-winforms-guis-in-powershell/)
* [PowerShell 技能连载 - 创建简单的 UI - 叹为观止](http://blog.vichamp.com/2016/12/28/creating-simple-uis/)
* [PowerShell 技能连载 - 调整简单界面 - 叹为观止](http://blog.vichamp.com/2016/12/28/adjusting-simple-uis/)
* [www.tk4479.net/FrankGGH/article/details/7334924](http://www.tk4479.net/FrankGGH/article/details/7334924)
* UI自动化：
* [powershell推荐阅读:使用 Windows PowerShell 实现 UI 自动化 - YOKE-HOME](https://yoke88.wordpress.com/2007/12/13/powershell推荐阅读使用-windows-powershell-实现-ui-自动化/)
* 计划任务：
* [启动powershell脚本在远程机器运行_百度知道](https://zhidao.baidu.com/question/538894308.html)
* GridView 显示csv
* [Out-GridView官方用法](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-5.1)
* git搜索
* Csv  GridView  language:PowerShell
* 
* winForm1
* [使用Windows PowerShell创建WinForm程序 - clowwindy - 博客园](http://www.cnblogs.com/clowwindy/archive/2009/05/06/1450344.html)
* [使用Windows PowerShell创建WinForm程序 - 亚伦的日志 - 网易博客](http://25ie.blog.163.com/blog/static/1026232112010213027499/)
* [使用Windows PowerShell创建WinForm程序 - 阿里云](https://yq.aliyun.com/wenji/97517)
* winForm2
* [Powershell创建WinForm应用程序 - 与你心飞 - ITeye博客](http://hongzhguan.iteye.com/blog/1471953)
* git搜索 
* Function Show-WinForm language:PowerShell 
* Function Show WinForm example language:PowerShell 
* Function Grid WinForm example language:PowerShell 
* 
* pdf
* http://m.jb51.net/books/209514.html
* [Powershell: edit a ListViewItem](https://social.technet.microsoft.com/Forums/scriptcenter/en-US/43ba26cf-e27b-4c4c-8b46-c0d21cb5104a/powershell-edit-a-listviewitem?forum=ITCG)
* [Windows PowerShell in 24 Hours, Sams Teach Yourself - Timothy L. Warner - Google 鍥句功](https://books.google.com/books?id=apztCAAAQBAJ&pg=PT291&lpg=PT291&dq=Add+ItemClick+powershell&source=bl&ots=1ND4pF3Wfh&sig=009o1GHBBZzVjCUExcvlHNKUfp4&hl=zh-CN&sa=X&ved=0ahUKEwijhsGJwfvXAhVFKGMKHYexCfUQ6AEISjAE#v=onepage&q=Add%20ItemClick%20powershell&f=false)
* [Building Forms with PowerShell – Part 1 (The Form)](https://blogs.technet.microsoft.com/stephap/2012/04/23/building-forms-with-powershell-part-1-the-form/)
* [Dealing with Powershell Inputs via Basic Windows Form](https://www.codeproject.com/Articles/799161/Dealing-with-Powershell-Inputs-via-Basic-Windows-F)
* [使用Windows PowerShell创建WinForm程序-代码之家](http://www.daima234.com/8/14236.html) 
* 
* building forms with powershell part 3 
* good
* [Building Forms with PowerShell – Part 1 (The Form) – Something About Scripting](https://blogs.technet.microsoft.com/stephap/2012/04/23/building-forms-with-powershell-part-1-the-form/)
* [Building a UI using WPF and PowerShell, Part 2 -- Microsoft Certified Professional Magazine Online](https://mcpmag.com/articles/2016/05/05/wpf-and-powershell-part-2.aspx)
* [FormBorderStyle Enumeration (System.Windows.Forms)](https://msdn.microsoft.com/en-us/library/hw8kes41.aspx)
* [Building a PowerShell GUI (Part 2) - TechGenix](http://techgenix.com/building-powershell-gui-part2/)
* [Building a PowerShell GUI (Part 3) - TechGenix](http://techgenix.com/building-powershell-gui-part3/)
* [PowerShell GUI with HTML - Part 3 – Tiberriver256](http://tiberriver256.github.io/powershell/gui/html/PowerShell-HTML-GUI-Pt3/)
* [Part 3 Adding Tab Controls – Create your own SQL tools with PowerShell and windows forms - JamesDataTechQ](https://jamesdatatechq.wordpress.com/2015/01/13/part-3-adding-tab-controls-create-your-own-sql-tools-with-powershell-and-windows-forms/)


DSM(黑群晖),FreeNAS、Openfiler等免费系统
* [开源 NAS 操作系统不完全汇总 - GetNAS中文网](http://www.getnas.com/open-source-nas)
* [变废为宝，用旧电脑自己DIY组建 NAS 服务器 - jack_Meng - 博客园](http://www.cnblogs.com/mq0036/p/5281185.html)

dell 540台式 升级内存  
电脑型号	戴尔 Studio 540 台式电脑  (扫描时间：2016年05月22日) 
操作系统	Windows 7 旗舰版 64位 SP1 ( DirectX 11 )  
处理器	英特尔 酷睿2 四核 Q8200 @ 2.33GHz
主板	戴尔 0M017G ( 英特尔 4 Series 芯片组 - ICH10R )  
内存	6 GB ( 尔必达 DDR2 800MHz / 金士顿 DDR2 800MHz )  
主硬盘	英特尔 SSDSC2BW120H6 ( 120 GB / 固态硬盘 )  
显卡	ATI Radeon HD 4300/4500 Series ( 512 MB / 戴尔 )  
显示器	XXX0180 HDTV ( 40.2 英寸  )  
声卡	瑞昱 ALC888 @ 英特尔 ICH10  高保真音频  
网卡	瑞昱 RTL8168/8111/8112 Gigabit Ethernet   
* [不要Ghost和重装 两招把Win7克隆到SSD | 微型计算机官方网站 MCPlive.cn](http://www.mcplive.cn/index.php/article/index/id/11085/page/3)

* C split txt file offset by bytes
* [MongoDB中文社区 | 中文社区](http://www.mongoing.com/)
* [window平台安装MongoDB | 菜鸟教程](http://www.runoob.com/mongodb/mongodb-window-install.html)
* OpenCV计算机视觉编程攻略