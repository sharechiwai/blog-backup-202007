---
id: 2621
title: 'TSQL GetDate() Get current date without time &#8211; TSQL GetDate() 取日期不取時間'
date: 2012-11-29T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2621
permalink: '/2012/11/tsql-getdate-get-current-date-without-time-tsql-getdate-%e5%8f%96%e6%97%a5%e6%9c%9f%e4%b8%8d%e5%8f%96%e6%99%82%e9%96%93/'
categories:
  - MSSQL Tips and Tricks
---
今天需要寫一個功能把 要把當日的日期加進數據庫的資料上  
這個Field的**Data Type** 是 **DateTime**  
所以如果我使用 **GetDate**的話 會出現  
**2012-11-30 13:21:06.483**

但是我只是需要 **2012-11-30**  
那怎麼辦呢?

**解決方法**:  
在**SQL Server 2008** 或以上  
可以直接使用**Cast** 這個日期成 **Data Type Date**便可以了  
我們可以使用以下的 **TSQL Code**

[sql]  
SELECT CAST(GETDATE() AS DATE)  
[/sql]

如果你是使用較舊的版本的話  
我們需要把變數

[sql]  
SELECT CAST(CONVERT(VARCHAR, GETDATE(), 102) AS DATETIME)  
[/sql]

**E.G.**  
<img alt="Get Date return Date without time" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e25e7bdcc7d9446b9d2c29625fb5e9e7" width="478" height="274" />  
Hope you find it useful