---
layout: post
title:  "Resize Chrome Window Automatically"
date:   2017-11-08 17:10:51 +0800
categories:  
tags: 
    - powershell

---

dependent on `sharex.exe`

### Resize Chrome Window Automatically ###
Here are two ways to accomplish this: `ChromeDriver` in selenium and `MS UI Automation`.   
Not Win32 API , Win32 API cant operate chrome window.   

Chromium
download_git_step1

DownloadSeluniumInOut


```
pip install selenium
pip install -U pyautoit
```
selenium.common.exceptions.WebDriverException: Message: 'chromedriver.exe' executable needs to be in PATH. Please see https://sites.google.com/a/chromium.org/chromedriver/home



simulate `window` + `d`
```python
autoit.send("#d")
```
	
watchdog



#### 参考 ####

