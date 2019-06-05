---
id: 3163
title: 'Titanium Studio\http://127.0.0.1:8020\index.html&#8221; not found. Would you like to create this file.'
date: 2014-05-03T00:00:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3163
permalink: /2014/05/titanium-studiohttp127-0-0-18020index-html-not-found-would-you-like-to-create-this-file/
categories:
  - Titanium studio
tags:
  - Titanium Studio TroubleShooting
---
今天嘗試使用**Titanium Studio** 的**Dashboard**上的 &#8220;**Learn**&#8221; -> &#8220;**Videos**&#8221; 來學習 **Titanium Studio**  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2902/14050438109_6b35974219_z.jpg?resize=625%2C423" alt="Titanium Studio Dashboard" width="625" height="423" data-recalc-dims="1" />  
但是當我按下時他彈出了以下的錯誤信息..  
&#8220;**Titanium Studio\http://127.0.0.1:8020\index.html&#8221; not found. Would you like to create this file.**&#8221;

<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2898/14235331675_3489f7b790_z.jpg?resize=591%2C332" alt="Would you like to create this file?" width="591" height="332" data-recalc-dims="1" /> 

還問我想不想建立這個檔案..Etc  
之後發現其實是因為我把**Notepad**設定去**HTML** 檔案的預設程式..  
所以當Titanium 嘗試開啟這檔案時嘗試使用**Notepad**開啟一個由**Titanium**的**Server** Dynamic 建立的一個檔案..  
所以便出現這個錯誤信息了..  
**解決方法**

只要把**HTML檔案的預設程式轉為任何一個瀏覽器**便可以了

**E.g.**  
在HTML檔案上**Mouse Right Click**之後選擇 &#8220;**Open with&#8230;** / **選擇開啟程式**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2921/14050586857_b9599fe3e3_z.jpg?resize=553%2C495" alt="Open with" width="553" height="495" data-recalc-dims="1" /> 

在&#8221;**Open with&#8221;** **windows** 上選擇一個預設的瀏覽器便可以了  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2920/14257354113_1fe8917f37_z.jpg?resize=587%2C486" alt="Open with Dialog" width="587" height="486" data-recalc-dims="1" /> 

Hope you find it useful