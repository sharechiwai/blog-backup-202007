---
id: 3573
title: 'Android Studio Cannot detect LG G4 Device &#8211; 電腦上執行ADB devices認不到 LG G4'
date: 2016-01-26T00:00:58+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3573
permalink: '/2016/01/android-studio-cannot-detect-lg-g4-device-%e9%9b%bb%e8%85%a6%e4%b8%8a%e5%9f%b7%e8%a1%8cadb-devices%e8%aa%8d%e4%b8%8d%e5%88%b0-lg-g4/'
categories:
  - Android
tags:
  - Android
---
終於換了手機了  
最近再次開始寫**Android**程式  
誰不知..**LG G4** 開啟了**Developer Mode**  
但是當我執行 指令去看看這個**device** 是不是連接到電腦時卻認不到

<pre>adb devices
</pre>

做了一會Research 後 發現.  
原來是**需要安裝驅動程式**/ **Driver** 的

**解決方法**:  
我們可以到以下連結之後填上 **手機的Model Number**  
不是 **LG G4** 而是 再細分的形號號碼 E.G.**H818N** 這是L**G G4 的雙咭版的Model Number**  
<a href="http://www.lg.com/hk/support/software-manuals" target="_blank">http://www.lg.com/hk/support/software-manuals</a>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1595/24718242661_9a4518df25_z.jpg?resize=593%2C640" alt="LG Hong Kong Download " width="593" height="640" data-recalc-dims="1" /> 

下載**Driver** 之後安裝後 再次執行  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1457/24454716150_2f62381f92_z.jpg?resize=625%2C382" alt="Installed LG G4 Driver" width="625" height="382" data-recalc-dims="1" /> 

<pre>adb kill-server
和
adb devices
</pre>

便可以了認到手機了  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1615/24724041406_d0b2280ac0_z.jpg?resize=261%2C120" alt="adb devices LG G4" width="261" height="120" data-recalc-dims="1" /> 

Hope you find it useful