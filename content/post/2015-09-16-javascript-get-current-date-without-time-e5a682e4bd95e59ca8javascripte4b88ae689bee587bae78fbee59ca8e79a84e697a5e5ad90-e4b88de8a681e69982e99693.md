---
id: 3507
title: 'Javascript get Current Date without time &#8211; 如何在Javascript上找出現在的日子.. 不要時間'
date: 2015-09-16T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3507
permalink: '/2015/09/javascript-get-current-date-without-time-%e5%a6%82%e4%bd%95%e5%9c%a8javascript%e4%b8%8a%e6%89%be%e5%87%ba%e7%8f%be%e5%9c%a8%e7%9a%84%e6%97%a5%e5%ad%90-%e4%b8%8d%e8%a6%81%e6%99%82%e9%96%93/'
categories:
  - Javascript
tags:
  - Javascript Tips and tricks
---
今天又為自己寫下一些筆記..  
很多時候都需要為網頁的一些 **Form** 或其他功能去埴上**今天/現時**的**日期**..  
很多時候的**default**/**預計功能**都會自動加上時間..  
有時就是因為這些 時間令到一些功能有錯誤..  
**E.G.** 例如你想比較兩個日子

**解決方法**十分簡單  
我們可使用 <span style="color: #008000;"><strong>new Date().toJSON()</strong> </span>來 輸出  
&#8220;**2015-08-21T14:46:06.729Z**&#8221;  
之後用<span style="color: #008000;"><strong>slice(0,10)</strong></span> 取出 日期的字串  
之後我們便可以用<span style="color: #008000;"><strong>new Date()</strong></span>來把這個日子轉為**javascript**的 日子**object** 以方便之後處理

<pre>Console.log(new Date().toJSON());
// result: "2015-08-21T14:46:06.729Z"
</pre>

<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/704/20810927086_b0451a8395_z.jpg?resize=259%2C80" alt="Javascript new Data().toJSON() result" width="259" height="80" data-recalc-dims="1" /> 

<pre>console.log(new Date().toJSON().slice(0,10));
// 2015-08-24
</pre>

把他轉為一個**Date**的**Object**

<pre>var currentDate = new Date().toJSON().slice(0,10)
// result "2015-08-21"
Console.log(currentDate);
</pre>

<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5818/20216227903_26905c39d6_z.jpg?resize=409%2C44" alt="Convert Date String to Javascript Date Object" width="409" height="44" data-recalc-dims="1" /> 

Hope you find it useful