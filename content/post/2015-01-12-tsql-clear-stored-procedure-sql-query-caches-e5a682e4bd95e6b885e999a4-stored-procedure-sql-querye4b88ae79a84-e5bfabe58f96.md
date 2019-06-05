---
id: 3359
title: 'TSQL Clear Stored Procedure / SQL Query Caches &#8211; 如何清除 Stored Procedure / SQL Query上的 快取'
date: 2015-01-12T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3359
permalink: '/2015/01/tsql-clear-stored-procedure-sql-query-caches-%e5%a6%82%e4%bd%95%e6%b8%85%e9%99%a4-stored-procedure-sql-query%e4%b8%8a%e7%9a%84-%e5%bf%ab%e5%8f%96/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Stored Procedure
  - TSQL
---
雖然自己還是在香港渡假中..  
但是公司有些他們覺得是和我有關的 programming 問題都會 **Google Hangout** Message我  
今天的問題是有一個Generate Report 的程式出Report的時間比之前的長很多..  
原定一小時入可以完成輸出Report這個動作..  
過了兩個小時還未能完成

所以我便覺得有機會是**Stored Procedure** 的 **Execution Plan Cache**左的問題  
因為這一次出 這一個Report 的數據是比平時出的大很多很多 [因為是幫一個公司最大的客出Report.. 但的Size是佔公司客的 五分之一]

可能之前的 Data 比較細..所以**Clear Stored Procedure Caches** 應該可以解決這個問題

**解決方法**:

如何清除 **Stored procedure** 的 **Caches**

大家可以在 **SQL Server Management Studio** 上 選擇你想清除 **Stored procedure Caches** 的 Database  
之後執行 以下SQL 指令

<pre>DBCC FREEPROCCACHE
</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7466/16048587527_3448300d87_z.jpg?resize=257%2C78" alt="Clear TSQL Caches - DBCC FREEPROCCACHE" width="257" height="78" data-recalc-dims="1" />  
詳情可以參考以下網頁  
<a title="http://msdn.microsoft.com/zh-tw/library/ms174283.aspx" href="How%20to clear TSQL Caches" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms174283.aspx</a>

有時間再和大家分享如何只清除某一個Execution Plan的 &#8220;Caches/快取&#8221;

Hope you find it useful