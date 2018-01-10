---
layout: post
title:  "windows ffmpeg 录音 MP3"
date:   2017-11-14 05:28:49 +0800
categories:  
tags: 
---

首先需要安装一个软件,screen capture recorder

### MP3 ###
```
ffmpeg -f dshow -i audio="virtual-audio-capturer" G:\ibook\0\400\EN\record\yo.mp3
```

dummy: Immediate exit requested

```
ffmpeg -f dshow  -i video="screen-capture-recorder"  -r 20 -t 10 screen-capture.mp4 # -t 10 for 10 seconds recording
```

```
ffmpeg -f dshow  -i video="screen-capture-recorder"  -r 20 -t 10 G:\ibook\0\400\EN\record\screen-capture.mp4 # -t 10 for 10 seconds recording
```

[dshow @ 00000000005c7540] real-time buffer [screen-capture-recorder] [video inp
ut] too full or near too full (242% of size: 3041280 [rtbufsize parameter])! frame dropped!
    Last message repeated 1 times
PS C:\Program Files\Listary>




```
ffmpeg -f dshow -i audio="virtual-audio-capturer":video="screen-capture-recorder" G:\ibook\0\400\EN\record\yo.mp4
```



#### 参考 ####

* [rdp/screen-capture-recorder-to-video-windows-free: a free open source windows "screen capture" device and recorder (also allows VLC/ffmpeg and others to capture/stream desktop/audio)](https://github.com/rdp/screen-capture-recorder-to-video-windows-free)
* [DirectShow – FFmpeg](https://trac.ffmpeg.org/wiki/DirectShow)
* [FFmpeg Devices Documentation](http://ffmpeg.org/ffmpeg-devices.html)
* [使用ffmpeg录音 - Not-Bad - 博客园](http://www.cnblogs.com/farewell-farewell/p/6111756.html)
* [使用ffmpeg录音及桌面录像](http://qtchina.github.io/4/node_450.html)
* [FFMPEG在Windows下的屏幕录像录音 - Red Star of Sleep's Blog - ITeye博客](http://redstarofsleep.iteye.com/blog/2146555)
* LIST2
* [How do I set up and use ffmpeg in Windows? - Video Production Stack Exchange](https://video.stackexchange.com/questions/20495/how-do-i-set-up-and-use-ffmpeg-in-windows)
* [Running cmd in python (ffmpeg) - Stack Overflow](https://stackoverflow.com/questions/16748148/running-cmd-in-python-ffmpeg)
* [Starting and stopping an ffmpeg pipeline in python - Stack Overflow](https://stackoverflow.com/questions/26024552/starting-and-stopping-an-ffmpeg-pipeline-in-python)
* [Stop an ffmpeg process · Issue #11 · Ch00k/ffmpy](https://github.com/Ch00k/ffmpy/issues/11)
* [Zulko/moviepy: Video editing with Python](https://github.com/Zulko/moviepy)
* [jiaaro/pydub: Manipulate audio with a simple and easy high level interface](https://github.com/jiaaro/pydub)
* [Python - Record MP3 - Raspberry Pi Forums](https://www.raspberrypi.org/forums/viewtopic.php?f=32&t=81777)
* [mikeboers/PyAV: Pythonic bindings for FFmpeg.](https://github.com/mikeboers/PyAV)
* [^c终止批处理操作吗（Y/N）-CSDN论坛](http://bbs.csdn.net/topics/390830109)
* [rajivepandey/MP3RecorderJS: Record MP3 (and WAV) files in the browser using JavaScript and HTML](https://github.com/rajivepandey/MP3RecorderJS)
* [Recording a mp3 stream with FFMPEG and drop-outs - Stack Overflow](https://stackoverflow.com/questions/7441686/recording-a-mp3-stream-with-ffmpeg-and-drop-outs)
