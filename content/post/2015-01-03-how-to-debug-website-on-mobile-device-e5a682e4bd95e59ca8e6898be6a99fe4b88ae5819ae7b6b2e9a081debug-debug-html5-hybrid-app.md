---
id: 3337
title: 'How to Debug website on Mobile Device &#8211; 如何在手機上做網頁debug / debug HTML5 Hybrid App'
date: 2015-01-03T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3337
permalink: '/2015/01/how-to-debug-website-on-mobile-device-%e5%a6%82%e4%bd%95%e5%9c%a8%e6%89%8b%e6%a9%9f%e4%b8%8a%e5%81%9a%e7%b6%b2%e9%a0%81debug-debug-html5-hybrid-app/'
categories:
  - Ionic Framework
tags:
  - Google Chrome
  - Hybrid App
  - ionic troubleshooting
---
最近開始研究使用**Ionic Framework** 來開發一些**Hybrid App** [用**HTML5**/ **Javascript** / **CSS** 和一些 Library 來開發..之後可以**Compile** 為 **Android**/**IOS**/**Windows** Phone 的應該程式的 開發工具]  
不久之後便發現要Debug這些**Hybrid App**很像不太容易..  
因為他們不像可以在**Android Studio**上**Debug**..  
他們又沒有**Console Windows**可以用來檢查 **Console.log**的結果

做了一會research之後發現

原來我們可以使用**Google Chrome** 來 Debug我們手機上的網頁的

**解決方法**:  
我們可以在**Google Chrome**的 **Address bar** 上輸入以下網址

&#8220;<span style="color: #008000;"><strong>chrome://inspect/#devices</strong></span>&#8221;

e.g. try the link below  
<a title="Chrome Inspect Devices" href="chrome://inspect/#devices" target="_blank"><strong>chrome://inspect/#devices</strong></a>

之後可以按一下**Inspect** 去 選擇**inspect**那一個 **Web App**或 **Website  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7548/15954813728_25ec855d06_z.jpg?resize=577%2C364" alt="Chrome Inspect devices" width="577" height="364" data-recalc-dims="1" />  
** 

之後便可以像平時 debug website 一樣 debug這個 Web App或 Website 了  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7490/16141509202_eec5617f68_z.jpg?resize=625%2C295" alt="Chrome Developer Tools - Mobile Web App" width="625" height="295" data-recalc-dims="1" /> 

Hope you find it useful

<!-- Tech-Blog-bottom-Content-336x280 -->

  
<ins class="adsbygoogle"></ins> style=&#8221;display:inline-block;width:336px;height:280px&#8221;  
data-ad-client=&#8221;ca-pub-4266560994470212&#8243;  
data-ad-slot=&#8221;3788424641&#8243;>