---
layout: post
title:  "Missing File named "bnc-lemma.txt""
date:   2017-11-09 13:29:53 +0800
categories:  
tags: 
    - english

---

# Missing File named "bnc-lemma.txt" #
Great work first of all! I was toying around with this. 
To be honest I had trouble getting your example to work. 
## Environment
system: win7 x64
IDE: Wing IDE 
python version: Python 2.7.10
## Report
### def test4():
An exception is thrown, when running  `linguist.py` . See image below. 
![](https://i.imgur.com/TYjFCyD.png)
The file named "bnc-lemma.txt" doesn't exists.

### def test2(): & def test3():
Missing module named `ascmini`
![](https://i.imgur.com/VDjvii7.png)
And `pip` can't get the module. 
```
PS C:\Program Files\Listary> pip install ascmini
You are using pip version 6.1.1, however version 9.0.1 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
Collecting ascmini
  Could not find a version that satisfies the requirement ascmini (from versions
: )
  No matching distribution found for ascmini
PS C:\Program Files\Listary>
```

