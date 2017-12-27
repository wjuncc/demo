---
layout: post
title:  "Get Css Definition"
date:   2017-11-07 10:53:27 +0800
categories:  
tags: 
    - powershell

---

### Get Css Definition  ###

Effect:

![](https://i.imgur.com/J9hYl0N.gif)

[](https://www.w3.org/TR/css-flexbox-1/)
In Git, I found a project names [CSS Validator Testsuite]() which could be the source of Css Definition. This project was created by w3c 4 years ago.

### Something useful: ###

* [tutorialspoint](https://www.tutorialspoint.com/css/css_azimuth.htm)
* [w3schools](https://www.w3schools.com/cssref/css_ref_aural.asp)

Then download the project code:
 
```ps
cd E:\n\learn\css
git clone https://github.com/w3c/css-validator-testsuite.git

```
and local directory:   
E:\n\learn\css\css-validator-testsuite\properties\positive\background-color

[search in w3c](https://github.com/search?p=2&q=org%3Aw3c+flex-direction&type=Code)
flex-direction
css-validator-testsuite/properties/positive/flex-direction/css3/001.css
E:\n\learn\css\css-validator-testsuite\properties\positive


read the content of each text 

![](https://i.imgur.com/xXoGkow.png)
![](https://i.imgur.com/11zwGSd.png)
![](https://i.imgur.com/drwpA9D.png)

figure 1-3 convert the text in 001.css to property definite code in actionscript each line.


![](https://i.imgur.com/mAyDoLQ.png)

The repeated names of css property reveals the version of proprty has not only one but many. The repeat count equal the version's.
For example,`azimuth`has 2 version named `css2` and `css21`, but `background-color` has 4 version `css1`,`css2`,`css3` and `css21`, 
    
about `azimuth`  
![](https://i.imgur.com/9h92XG3.png)
![](https://i.imgur.com/Z5QwzPq.png)

about `background-color`  
![](https://i.imgur.com/2vxO817.png)
![](https://i.imgur.com/4S4f6ia.png)

At last export all as file.

![](https://i.imgur.com/3mtOV4E.png)

![](https://i.imgur.com/Uw6cKHm.png)


In this way, I get the   
![](https://i.imgur.com/Oss4SA4.png)

But there are several mistakes :  
### Error from Parentheses,  Error from Quotation marks   ###

Before:
![](https://i.imgur.com/HWW0e92.png)

After:
![](https://i.imgur.com/KNPqu2n.png)



#### Error from Number:   ####

from `E:\n\learn\css\css-validator-testsuite\properties\positive\z-index\css21\001.css` 
to `E:\n\learn\css\css-validator-testsuite\properties\v66\out\Vz_index.as`
![](https://i.imgur.com/hnERvyd.png)


Before:
![](https://i.imgur.com/zn6N7aD.png)

After:
![](https://i.imgur.com/W2zXZ3z.png)



from `E:\n\learn\css\css-validator-testsuite\properties\positive\top\css3\001.css` 
to `E:\n\learn\css\css-validator-testsuite\properties\v66\out\Vtop.as`

#### Error from Percent Sign :   ####
Before:
![](https://i.imgur.com/LppHX0I.png)

After: