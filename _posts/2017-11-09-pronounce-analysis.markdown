---
layout: post
title:  "pronounce analysis"
date:   2017-11-09 03:51:39 +0800
categories:  
tags: 
    - english

---




Phonogram is the key to open a new world.

## Plans ##

* choose one source, eg. audiobook novel best	[`The Most Dangerous Game` (1924) ](https://en.wikipedia.org/wiki/The_Most_Dangerous_Game)

and then:
### Plan A ### 
* collect word list.
* get phonogram of each word.
* reorder by vowel and consonant
* 



split letter 

ODE3 (Oxford Dictionary of English ) 


### Convert mdx Data ###

* dictionary->mdx [IDMSKconv](https://github.com/superfan89/IDMSKconv)
* mdx->txt getdict


### Plan B ###
* recording system sound in English By TTS.save as mp3
* generate a million of pronounce analysis pieces data from mp3
* collect same type of pieces data
* 

#### Ref ####

* [Vowel - Wikipedia](https://en.wikipedia.org/wiki/Vowel)
* [英语国际音标 - 维基百科，自由的百科全书](https://zh.wikipedia.org/wiki/英語國際音標)
* [clairemoorecantwell/EnglishStressStatistics: Series of tools for doing analysis of the English stress system with the CMU pronouncing dictionary](https://github.com/clairemoorecantwell/EnglishStressStatistics)
* [Claire Moore-Cantwell (SFU)](http://clairemoorecantwell.org)
* [The CMU Pronouncing Dictionary](http://www.speech.cs.cmu.edu/cgi-bin/cmudict)


元音音标，指发音时不受到发音器官的阻碍发出的声音，国际音标里，元音音标共20个：
单元音：
```
/a:/   /כ:/   /ɜː/   /i:/   /u:/   /æ/
/ʌ/   /ɒ/   /ə/   /ɪ/   /ʊ/   /e/
```
双元音：
```
/eɪ/   /aɪ/   /כɪ/   /əu/
/au/   /eə/   /ɪə/   /uə/  
```

The data structure of word `abandon`, keyword of phonogram is `phonetic`:
```json
{'definition': u'n. the trait of lacking restraint or control; reckless freedom from inhibition or worry\nv. forsake, leave behind\nv. give up with the intent of never claiming again\nv. stop maintaining or insisting on; of ideas or claims', 'word': u'abandon', 'bnc': 2057, 'exchange': u'd:abandoned/p:abandoned/i:abandoning/3:abandons', 'sw': u'abandon', 'pos': u'', 'detail': None, 'oxford': 1, 'frq': 2182, 'tag': u'gk cet4 cet6 ky toefl gre', 'phonetic': u"\u04d9'b\xe6nd\u04d9n", 'collins': 3, 'translation': u'vt. \u653e\u5f03, \u629b\u5f03, \u9057\u5f03, \u4f7f\u5c48\u4ece, \u6c89\u6eba, \u653e\u7eb5\nn. \u653e\u4efb, \u65e0\u62d8\u675f, \u72c2\u70ed', 'audio': u'', 'id': 2689}

```
powershell script:
```powershell
cd G:\ibook\0\400\EN\DIC\git
git clone https://github.com/skywind3000/ECDICT.git

cd G:\ibook\0\400\EN\DIC\git\backup
git clone https://github.com/skywind3000/ECDICT.git


cd G:\ibook\0\400\EN\DIC\git
git clone https://github.com/skywind3000/vim.git

cd G:\ibook\0\400\EN\DIC\git
git clone https://github.com/p9s/fetch_english_word_phonogram

cd G:\ibook\0\400\EN\DIC\git
git clone https://github.com/michaelyou/a-python-a-day

```

[Good English-Chinese Database:ECDICT](https://github.com/skywind3000/ECDICT.git) is a big app, downloaded in 10 minutes:
```powershell
Receiving objects:  42% (165/390), 217.87 MiB | 1.33 MiB/s
```

A table sppear in this code online but not local jekyll.
```
| 字段 | 解释 |
|------|------|
| word | 单词名称 |
```
### ELSE ###
```
pip install nltk
Successfully installed nltk-3.2.5
```

run this 1st: 
```python
import nltk
nltk.download('wordnet')
``` 

how to install `mysqlclient`? not `pip install MySQLdb` but `pip install mysqlclient`



#### 参考 ####

* [每天一个python小程序(5)--找出最重要的单词 - Youmai の Blog](https://michaelyou.github.io/2015/02/02/每天一个python小程序-5/)
* [a-python-a-day/no.4 at master · michaelyou/a-python-a-day](https://github.com/michaelyou/a-python-a-day/tree/master/no.4)
* [每天一个python小程序(4)--统计单词频数 - Youmai の Blog](https://michaelyou.github.io/2015/02/02/每天一个python小程序-4/)
* [Richard Connell - Wikipedia](https://en.wikipedia.org/wiki/Richard_Connell)
