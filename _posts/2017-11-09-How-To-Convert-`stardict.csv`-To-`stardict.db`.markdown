---
layout: post
title:  "How To Convert `stardict.csv` To `stardict.db`?"
date:   2017-11-09 13:22:54 +0800
categories:  
tags: 
    - english

---

## How To Convert `stardict.csv` To `stardict.db`? ##

This piece works well:
```python
	srcname = ur"bnc-words.csv"
	dstname = ur"bnc-words.sqlite"
	
	convert_dict(dstname, srcname)
```

Differ from the file `stardict.csv` which was extracted from `stardict.7z`:
 
```python
	srcname = ur"stardict.csv"
	dstname = ur"stardict.sqlite"
	
	convert_dict(dstname, srcname)
```
![](https://i.imgur.com/0WLRUuF.png)
thrown an `MemoryError`:
![](https://i.imgur.com/uZqOsw6.png)
thrown same error when running a command-line,:
![](https://i.imgur.com/eBVYVkL.png)


