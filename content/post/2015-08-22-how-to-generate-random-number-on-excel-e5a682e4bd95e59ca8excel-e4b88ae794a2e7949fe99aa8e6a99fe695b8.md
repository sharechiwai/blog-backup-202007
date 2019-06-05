---
id: 3479
title: 'How to generate Random number on Excel &#8211; 如何在Excel 上產生隨機數'
date: 2015-08-22T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3479
permalink: '/2015/08/how-to-generate-random-number-on-excel-%e5%a6%82%e4%bd%95%e5%9c%a8excel-%e4%b8%8a%e7%94%a2%e7%94%9f%e9%9a%a8%e6%a9%9f%e6%95%b8/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Excel
  - Excel Function
---
有時想使用**Excel**去做一些隨機數據來做一些測試  
那麼如何在**Excel** 上產生隨機數

**解決方法**十分簡單..我們可以使用**Excel**的 **RAND** 功能來產生隨機數  
<span style="color: #008000;"><strong>RAND()</strong> </span>這個功能會產生 一個0 &#8211; 1 的 隨機數..包含小數點的  
如果我們想產生 一個1 &#8211; 10 的 隨機數  
那麼我們便要用<span style="color: #008000;"><strong> RAND()*(10)+1</strong></span> 了  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/332/19892613503_5547d19da9_z.jpg?resize=445%2C110" alt="Excel Generate Random Number RAND()" width="445" height="110" data-recalc-dims="1" /> 

如果我們不想有小數點..  
可以用<span style="color: #008000;"><strong>TRUNC</strong> </span>這個功能

<pre>=TRUNC(RAND()*(10)+1)
</pre>

Hope you find it useful