---
id: 3181
title: TSQL Convert Date to hh:mm:ss – 在TSQL 上 如何把 DataTime 轉成 hh:mm:ss 呢?
date: 2014-05-15T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3181
permalink: '/2014/05/tsql-convert-date-to-hhmmss-%e5%9c%a8tsql-%e4%b8%8a-%e5%a6%82%e4%bd%95%e6%8a%8a-datatime-%e8%bd%89%e6%88%90-hhmmss-%e5%91%a2/'
categories:
  - MSSQL Tips and Tricks
---
今天需要寫一個Query 來把一個**DateTime** Field 分開為 **日期**和**時間**兩個Field  
E.G.  
**2014-05-01** 和 **12:34:56**

現在可以再用在網上找尋這個解決的方法

大家可以到以下網址參考之前有關轉換DateTime Field為 YYYY-MM-DD 的網誌

[**TSQL Convert Date to YYYY-MM-DD – 在TSQL 上 如何把 DataTime 轉成 YYYY-MM-DD 呢?**](http://blog.sharechiwai.com/2013/04/tsql-convert-date-to-yyyy-mm-dd-%e5%9c%a8tsql-%e4%b8%8a-%e5%a6%82%e4%bd%95%e6%8a%8a-datatime-%e8%bd%89%e6%88%90-yyyy-mm-dd-%e5%91%a2/ "TSQL Convert Date to YYYY-MM-DD – 在TSQL 上 如何把 DataTime 轉成 YYYY-MM-DD 呢?")

那麼如何把 **DataTime** 轉成 **hh:mm:ss** 呢?

 **解決方法**十分簡單.

我們可以用**Convert**這個功能 之後把**Format**的設定為**8**便可以了

E.G.

<pre>SELECT CONVERT(VARCHAR(10), GetDate(),8)
</pre>

<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5569/14385848615_4b15c814c9_z.jpg?resize=625%2C186" alt="TSQL Convert DateTime to hh:mm:ss" width="625" height="186" data-recalc-dims="1" /> 

**Sample Code**:

<pre>DECLARE @CurrentDateTime DATETIME = GETDATE()
CONVERT(VARCHAR(10), @CurrentDateTime,126) AS [YYYY-MM-SS],
SELECT @CurrentDateTime DefaultDate,
CONVERT(VARCHAR(10), @CurrentDateTime,8) AS [hh:mm:ss]
</pre>

Hope you find it useful