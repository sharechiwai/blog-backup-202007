---
id: 3460
title: 在Android 上怎樣可以知道用戶手機的屏幕資訊 Android Detect Screensize resolution
date: 2015-08-12T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3460
permalink: '/2015/08/%e5%9c%a8android-%e4%b8%8a%e6%80%8e%e6%a8%a3%e5%8f%af%e4%bb%a5%e7%9f%a5%e9%81%93%e7%94%a8%e6%88%b6%e6%89%8b%e6%a9%9f%e7%9a%84%e5%b1%8f%e5%b9%95%e8%b3%87%e8%a8%8a-android-detect-screensize-resolution/'
categories:
  - Android
tags:
  - Mobile Development
---
大家可以使用**getWindowManager**的 **getMetrics** 功能

<pre>DisplayMetrics metrics = new DisplayMetrics();
getWindowManager().getDefaultDisplay().getMetrics(metrics);
</pre>

我們可以使用 **metrics.toString()** 去輸出**DisplayMetrics**的Summary

Hope you find it useful