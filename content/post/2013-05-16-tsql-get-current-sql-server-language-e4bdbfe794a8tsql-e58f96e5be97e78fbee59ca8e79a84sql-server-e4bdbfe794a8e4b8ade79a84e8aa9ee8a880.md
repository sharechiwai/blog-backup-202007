---
id: 2874
title: 'TSQL Get Current SQL Server language &#8211; 使用TSQL 取得現在的SQL Server 使用中的語言'
date: 2013-05-16T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2874
permalink: '/2013/05/tsql-get-current-sql-server-language-%e4%bd%bf%e7%94%a8tsql-%e5%8f%96%e5%be%97%e7%8f%be%e5%9c%a8%e7%9a%84sql-server-%e4%bd%bf%e7%94%a8%e4%b8%ad%e7%9a%84%e8%aa%9e%e8%a8%80/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
在安**裝Microsoft SQL Server 2012**之後 的第一個動作是 檢查**SQL Server**的設定  
很多時候公司上的**SQL Server** 出現的問題都是和**Date Format**有關的  
E.G.  
我們會執行以下的 **TSQL**

[sql]  
&#8212; Show current language  
SELECT @@language  
&#8212; create date from string  
DECLARE @dateSample datetime = &#8217;06/09/2013&#8242;;  
SELECT @dateSample;  
[/sql]

**US English的 2013年6月9日**是這樣顯示的  
[<img class="alignnone size-full wp-image-2875" alt="US_English Date" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/USEngDate.jpg?resize=232%2C154" width="232" height="154" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/USEngDate.jpg)  
**而British English 的 2013年6月9日**是這樣顯示的

[<img class="alignnone size-full wp-image-2876" alt="British English Date" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/BritishEngDate.jpg?resize=272%2C172" width="272" height="172" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/BritishEngDate.jpg)  
有時候開發人員會用一些很奇怪的方法去嘗試以字串的方法來輸入日期..  
很多時候因為大家都以為**Database**是用 **Brisith English**  
但是其實**Database** 是用**US English** 的時候..  
他們的功能都會出現錯誤..

所以為免這個情況的出現..  
我多數會檢查一下 **Database** 現在的語言是什麼&#8230;  
我們可以執行以下的 **TSQL** 來取得現在的語言

[sql]  
SELECT @@language  
[/sql]

**結果**  
[<img class="alignnone size-full wp-image-2877" alt="TSQL Get Current Language" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TSQLLanguage.jpg?resize=231%2C134" width="231" height="134" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TSQLLanguage.jpg)  
如果不是我想要的那一個的時候我們可以嘗試更改!

Hope you find it useful