---
id: 3172
title: 'Where is the Microsoft.Exchange.WebServices References &#8211; Microsoft.Exchange.WebServices 的參考在那裡?'
date: 2014-05-08T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3172
permalink: '/2014/05/where-is-the-microsoft-exchange-webservices-references-microsoft-exchange-webservices-%e7%9a%84%e5%8f%83%e8%80%83%e5%9c%a8%e9%82%a3%e8%a3%a1/'
categories:
  - .Net Tips And Tricks
tags:
  - Microsoft Exchange Web Service
  - Microsoft.Exchange.WebServices
  - NuGet
---
今天需要把一個用了**Microsoft Exchange Web Services** 的程式 整合到一個正在開發中個**Centralise Web Service**上

其實工作不多..只需要複製和更新這個Module的程式碼到新的**Web Service**上便可以了

誰不知&#8230;開始不久便發了一個難題..就是怎麼可以把<span style="color: #008000;"><strong>Microsoft.Exchange.WebServices.dll</strong></span> 這個參考加進新的 程式上

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5075/14280964656_21391699b6_z.jpg?resize=316%2C56" alt="Require Microsoft.Exchange.WebServices Reference" width="316" height="56" data-recalc-dims="1" /> 

由於公司在今年之前都沒有一個好的**Documentation**的 習慣..  
所以沒有人知道怎樣可以加入這個**Reference**  
在 **Add Reference** 的**Windows** 上找不到這個參考

<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2923/14117447028_8330c0e8cd_z.jpg?resize=625%2C432" alt="Add Reference Windows" width="625" height="432" data-recalc-dims="1" /> 

做了一會兒Research 後發現原來解決方法十分簡單..

**解決方法:**  
我們可以使用**NuGet**來加入&#8221;<span style="color: #008000;"><strong>Microsoft.Exchange.WebServices.dll</strong></span>&#8221; 這個參考  
只要在**Visual Studio** 的**NuGet**上 Search &#8220;**Exchange**&#8221; 便可以找到了  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2915/14280964636_6d0f19c2ec_z.jpg?resize=625%2C418" alt="Microsoft Exchange Web Service Reference on NuGet" width="625" height="418" data-recalc-dims="1" /> 

安裝後在這個**Project**上的**Reference** 資料夾便可以找到這個 &#8220;**Microsoft.Exchange.WebServices.dll&#8221;**

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3705/14303528544_5428ac5582_z.jpg?resize=330%2C182" alt="Project Reference contain - Microsoft.Exchange.WebServices" width="330" height="182" data-recalc-dims="1" /> 

之前的程式怎樣加入 這個參考還是一個迷

Hope you find it useful