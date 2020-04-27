---
title: "FFmpeg convert resize video - 使用FFmpeg 來轉換視訊格式"
date: 2020-03-08T00:00:00+08:00
author: ShareChiWai
layout: post
categories:
  -
tags:
  - ffmpeg
  - Convert Video
  - Convert Audio
  - Free software
---

使用 `FFmpeg` 來轉換 Video 格式十分容易的  
首先要知道`FFmpeg` 可以轉換那些 format
大家可以執行以下的指令看看
```
ffmpeg -formats
```
或者參考以下網頁
https://www.ffmpeg.org/ffmpeg-formats.html

https://www.ffmpeg.org/general.html#Supported-File-Formats_002c-Codecs-or-Features

轉換Video format 十分簡單  

以下是一些有用的command  

`mp4 to mkv`
```
ffmpeg -i \
[input]mp4] \
-vcodec copy \
-acodec copy \
[output.mkv]
```

`mkv to mp4`
```
ffmpeg -i \
[input.mkv] \
-c copy \
[output.mp4]
```

`to be updated`


