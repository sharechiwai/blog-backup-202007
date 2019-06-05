---
id: 3166
title: 'TSQL Reset Identity auto-increment number &#8211; TSQL 上怎樣可以重設 自動遞增數的種子數值'
date: 2014-05-05T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3166
permalink: '/2014/05/tsql-reset-identity-auto-increment-number-tsql-%e4%b8%8a%e6%80%8e%e6%a8%a3%e5%8f%af%e4%bb%a5%e9%87%8d%e8%a8%ad-%e8%87%aa%e5%8b%95%e9%81%9e%e5%a2%9e%e6%95%b8%e7%9a%84%e7%a8%ae%e5%ad%90%e6%95%b8/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今天在公司寫的一個**Module** 需要每天都把公司其中一個數據庫Table上大部份的資料複製一次到這個暫用的**Table**上分析  
之後再出一個報告  
由于資料數量每天都有數百萬條&#8230;所以不知道會不會有一天**auto-increment** 的值大過**Integer**的值  
導致出現  
&#8220;<span style="color: rgb(255, 0, 0);"><strong>Arithmetic overflow error converting expression to data type int.</strong></span>&#8221;  
的錯誤信息  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2911/14064981480_a60f30f91a_z.jpg?resize=469%2C75" alt="Arithmetic overflow error converting expression to data type int" width="469" height="75" data-recalc-dims="1" /> 

所以便在做research 看看有沒有方法可以重設這個**Auto-Increment**的值  
每當資料重新**Import** 時重設他做****  
**解決方法**..  
原來我們是可以使用 &#8220;**DBCC CHECKIDENT**&#8221; 這個功能來**檢查**和**重設Auto-increment** 的值的  
E.G.  
**檢查現在Auto-Increment的值**  
<span style="color: rgb(0, 128, 0);"><strong>DBCC CHECKIDENT (&#8216;TableName&#8217;);</strong></span>  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5558/14271769633_8833b88592_z.jpg?resize=600%2C137" alt="TSQL Check Identity value" width="600" height="137" data-recalc-dims="1" /> 

我使可以使用**RESEED**這個變數來重設 **Auto-Increment**的值

<span style="color: rgb(0, 128, 0);"><strong>DBCC CHECKIDENT (&#8216;TableName&#8217;, RESEED,0);</strong></span>  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5271/14064981510_84075c2ec3_z.jpg?resize=604%2C151" alt="TSQL Reseed Auto-increment Number" width="604" height="151" data-recalc-dims="1" /> 

**結果:**  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5114/14249408092_4863021c28_z.jpg?resize=361%2C92" alt="Reset Table Identity Field" width="361" height="92" data-recalc-dims="1" /> 

詳情可以參考以下網址  
<a href="http://technet.microsoft.com/en-us/library/ms176057.aspx" target="_blank">http://technet.microsoft.com/en-us/library/ms176057.aspx</a>

Hope you find it useful