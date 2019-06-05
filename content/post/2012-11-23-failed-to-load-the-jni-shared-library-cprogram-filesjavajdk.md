---
id: 2601
title: 'Failed to load the JNI Shared library &#8220;c:\Program Files\Java\jdk&#8221;'
date: 2012-11-23T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2601
permalink: /2012/11/failed-to-load-the-jni-shared-library-cprogram-filesjavajdk/
categories:
  - Android
tags:
  - eclipse
---
今天在新電腦上安裝**Eclipse**時出現了以下的錯誤信息  
<img alt="" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d3a2ed1aef634e53bf391eecae5d759f" width="478" height="313" /> 

&#8216;<span style="color: #ff0000;"><strong>Failed to load the JNI shared library &#8220;C:\Program Files\Java\jdk1.7.0_10\bin\..\jre\bin\server\jvm.dll&#8221;</strong></span>&#8216;

**解決方法**十分簡單  
原來Eclipse 的安裝設定是不可以把32bit 和 64bit  
的程式混合一起使用的

E.G.  
如果你已安裝的**Java JDK**是**32bit**的話  
你便要下載32bit 的**Eclipse** 來使用

如果你已安裝的**Java JDK**是64bit的話  
你便要下載64bit 的**Eclipse**

Otherwise 你便會遇到這個問題了

大家可以到**Eclipse**的Official Website  
[http://www.eclipse.org/downloads/](http://www.eclipse.org/downloads/ "Eclipse Download")

Hope you find it useful