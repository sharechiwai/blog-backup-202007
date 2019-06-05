---
id: 3239
title: 'New Relic Mulitple site on same server &#8211; 如何使用New Relic在同一個Server上來監測不同的Web Application / Domain 呢?'
date: 2014-06-18T00:00:34+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3239
permalink: '/2014/06/new-relic-mulitple-site-on-same-server-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8new-relic%e5%9c%a8%e5%90%8c%e4%b8%80%e5%80%8bserver%e4%b8%8a%e4%be%86%e7%9b%a3%e6%b8%ac%e4%b8%8d%e5%90%8c%e7%9a%84web-appli/'
categories:
  - 工作經驗/體驗/工作心得分享
tags:
  - VPS
---
公司久不久便會有**VPN**/ **Broadband**等 **Network**的問題  
老闆常常都說要買一些工具來**Monitor** 一下網絡的問題  
當公司網頁不能連接時 要有**SMS** 短信或 **EMAIL** 的通知..

之前聽過有一間公司**<a title="New Relic" href="http://newrelic.com/" target="_blank">New Relic </a>**有這個服務..  
<a title="New Relic" href="http://newrelic.com/" target="_blank">http://newrelic.com/</a>  
可惜沒有時間嘗試..今天終於在自己的**VPS** 上安裝了  
感覺良好&#8230;  
安裝和設定方法十分簡單.. 他的網頁上有**Video 教學**.十分清晰  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3836/14716591302_e1ec4f40e3_z.jpg?resize=625%2C344" alt="New Relic Dashboard" width="625" height="344" data-recalc-dims="1" /> 

因為我的**VPS** 上有多個**Web Application**的關係..  
那麼如何使用**New Relic**在同一個Server上來監測不同的**Web Application** / **Domain** 呢?

做了一會**Research** 後發現..

其實**解決方法**十分簡單..  
我們只需要在 **Root Folder** / **主文件夾**上 的 **.htaccess** 檔案上加上 一個 更新 **PHP** 的變數的 詞句便可以  
E.G.  
把 **newrelic.appname** 設定成你想在 **New Relic 網頁上想看到的名稱**便可以  
[我們需要在每一個想Monitor 的網頁上加上這些設定]

E.G.  
在這個Blog上的 **.htaccess** 檔案 加上

<pre>&lt;IfModule mod_php5.c&gt;
 php_value newrelic.appname "blog.sharechiwai.com"
&lt;/IfModule&gt;
</pre>

<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2928/14713706781_99ae49613b_z.jpg?resize=504%2C68" alt=".htaccess confic for New Relic multiple website on same server" width="504" height="68" data-recalc-dims="1" />  
當**Server Down**的時候我得到了以下的Email 警報  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3878/14736750143_9b53189678_z.jpg?resize=625%2C129" alt="New Relic Downtime alert" width="625" height="129" data-recalc-dims="1" /> 

Hope you find it useful