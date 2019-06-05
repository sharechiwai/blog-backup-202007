---
id: 3267
title: 'Ant &#8211; Unable to locate tools.jars. Expected to find it in'
date: 2014-07-05T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3267
permalink: /2014/07/ant-unable-to-locate-tools-jars-expected-to-find-it-in/
categories:
  - Ionic Framework
tags:
  - Apache Ant
  - ionic troubleshooting
  - troubleshooting
---
在完成安裝**Ant**之後  
嘗試在**Command Prompt**上執行**Ant** 看看安裝/設定有沒有問題  
很可惜當我執行 ant時 他出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Unable to locate tools.jars. Expected to find it in</strong></span>&#8221;

<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2903/14634009800_091f71af95_z.jpg?resize=625%2C157" alt="Unable to locate tools.jars. Expected to find it in" width="625" height="157" data-recalc-dims="1" />  
做了一會research後發現..  
這應該是**Environment Variables** /**環境變數** 設定的問題  
所以我便到  
&#8220;**Advanced System Settings**/**進階系統設定**&#8221; -> &#8220;**Advanced** tab/**進階** 分頁&#8221; ->&#8221;**Environment Variables** / **環境變數**&#8221; 按一下  
在之前的網誌有介紹如何修改&#8221;**Environment Variables** / **環境變數**&#8221; 有興趣的朋友可以到以下網誌參考  
<a href="http://blog.sharechiwai.com/2014/07/how-to-install-ant-on-windows-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e4%b8%8a%e5%ae%89%e8%a3%9dant/" rel="bookmark">How to install Ant on Windows – 如何在Windows 上安裝Ant</a>

之後選擇&#8221;**JAVA_HOME**&#8221; -> **Edit**/**修改**  
把原先設定下的**JAVA_HOME** path  
&#8220;<span style="color: #008000;"><strong>C:\Program Files\Java\jdk1.7.0_45\bin</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3889/14634160967_a73b43d795_z.jpg?resize=459%2C537" alt="Environment Variables -> JAVA_HOME Path" width="459" height="537" data-recalc-dims="1" /> 

轉成  
&#8220;<span style="color: #008000;"><strong>C:\Program Files\Java\jdk1.7.0_45</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3882/14634079578_2a020b704a_z.jpg?resize=562%2C580" alt="Environment Variable -> JAVA_HOME Path without bin folder" width="562" height="580" data-recalc-dims="1" /> 

便解決了 &#8220;**<span style="color: #ff0000;">Unable to locate tools.jars. Expected to find it in</span>**&#8221; 的問題了  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3916/14818343974_913048c3ac_z.jpg?resize=544%2C185" alt="Solved: Unable to locate tools.jars. Expected to find it in " width="544" height="185" data-recalc-dims="1" /> 

Hope you find it useful