---
id: 3452
title: Default android debug.keystore location
date: 2015-08-05T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3452
permalink: /2015/08/default-android-debug-keystore-location/
categories:
  - Android
tags:
  - Android
  - Android Tips and Tricks
  - Google API
---
今天嘗試在**Android Application** 上 **implement Google OAuth**  
當我去到**Google API Console** 嘗試建立一個 &#8220;**Android Key**&#8220;的時候  
他的Instruction說明要 找出**developer certificate** E.G. **Keystore** 的 **SHA1 fingerprint**  
之後加入**Google API Console**的**Config** 內  
&#8220;<span style="color: #008000;"><strong>keytool -list -v -keystore mystore.keystore</strong></span>

<span style="color: #008000;"><strong>Accept requests from an Android application with one of the certificate fingerprints and package names listed below:</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/323/20126738658_78414f6f4e_z.jpg?resize=625%2C417" alt="Configure Android Key" width="625" height="417" data-recalc-dims="1" /> 

**Release key**的 **Developer Certificate**/ **keystore**我知道在那裡..  
如果大家不知道怎樣建立

可以參考以下網誌  
<a href="http://blog.sharechiwai.com/2015/01/useful-command-for-android-development-1-%e4%b8%80%e4%ba%9b%e6%9c%89%e7%94%a8%e7%9a%84%e5%9c%a8%e9%96%8b%e7%99%bcandroid%e7%a8%8b%e5%bc%8f%e6%99%82%e5%b9%be%e6%9c%89%e7%94%a8%e7%9a%84%e6%8c%87/" target="_blank">怎樣建立 Android Developer Certificate Keystore</a>

做了一會research 終於發現了**debug.keystore** 存在那裡 大家的User資料夾內的 &#8220;**.android**&#8220;資料夾內  
大家可以到以下路徑看看

<pre>c:\users\{username你的使用者名稱}\.android\debug.keystore
</pre>

E.g.  
<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/311/20246437032_96687d89c6_z.jpg?resize=625%2C390" alt="Android Default Debug.Keystore" width="625" height="390" data-recalc-dims="1" />  
Hope you find it useful