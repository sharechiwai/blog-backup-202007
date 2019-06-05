---
id: 3341
title: 'Some useful ADB Command &#8211; 在開發Android /Tizen Application 時一些得重要的 ADB 指令'
date: 2015-01-05T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3341
permalink: '/2015/01/some-useful-adb-command-%e5%9c%a8%e9%96%8b%e7%99%bcandroid-tizen-application-%e6%99%82%e4%b8%80%e4%ba%9b%e5%be%97%e9%87%8d%e8%a6%81%e7%9a%84-adb-%e6%8c%87%e4%bb%a4/'
categories:
  - Android
tags:
  - ADB
  - FFOS
  - Firefox OS
  - Tizen
---
**ADB** &#8211; **Android Debug Bridge**  
&#8211; 用來**deploy**和**debug Android app**到 手機來測試的.. **FireFox OS** 和其實的 Mobile Application 很多也是用**ADB**的

以下有些我覺得很有用的 **adb 指令**想和大家分享

**adb devices**  
&#8211; 這個指令是用來列出..在電腦上所有連接的**實體**設備[**Physical devices**] **模擬器** [**Emulator**]

**adb kill-server**  
&#8211; 當你已經把**devices** 連接了電腦..但是 執行 &#8220;**adb devices**&#8220;時 沒有列出設備是.. 可以執行&#8221;**adb kill-server**&#8221; 去終止現在的**adb server**.. 嘗試去再啟動來認一下己連接的設備  
<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8682/16127090656_b664b7d3be_z.jpg?resize=415%2C198" alt="adb devices could not detect devices" width="415" height="198" data-recalc-dims="1" /> 

**adb start-server**  
&#8211; 這個指令通常會在執行&#8221;**adb kill-server**&#8221; 後執行.. 以用來啟動 **adb server  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7506/16152121672_e8b359de82_z.jpg?resize=564%2C437" alt="adb devices found devices" width="564" height="437" data-recalc-dims="1" />  
** 

當我的電腦認不到我的**device**時..  
我通常會不停到執行以下指令

<pre><span style="color: #008000;"><strong>adb kill-server</strong></span>
<span style="color: #008000;"><strong>adb start-server</strong></span>
<span style="color: #008000;"><strong>adb devices</strong></span>
</pre>

Hope you find it useful

<!-- Tech-Blog-bottom-Content-336x280 -->

  
<ins class="adsbygoogle"
     style="display:inline-block;width:336px;height:280px"
     data-ad-client="ca-pub-4266560994470212"
     data-ad-slot="3788424641"></ins>