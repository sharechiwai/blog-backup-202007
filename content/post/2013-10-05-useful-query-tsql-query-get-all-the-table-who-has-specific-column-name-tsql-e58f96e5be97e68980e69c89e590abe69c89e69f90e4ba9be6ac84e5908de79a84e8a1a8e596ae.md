---
id: 2944
title: 'Useful Query TSQL Query Get all the table who has specific Column name &#8211; TSQL 取得所有含有某些欄名的表單'
date: 2013-10-05T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2944
permalink: '/2013/10/useful-query-tsql-query-get-all-the-table-who-has-specific-column-name-tsql-%e5%8f%96%e5%be%97%e6%89%80%e6%9c%89%e5%90%ab%e6%9c%89%e6%9f%90%e4%ba%9b%e6%ac%84%e5%90%8d%e7%9a%84%e8%a1%a8%e5%96%ae/'
categories:
  - MSSQL Tips and Tricks
---
今天要幫公司的其中一個**資料庫**做 **Database Schema** 的更新

我們要找出資料庫上..的**Table** / **表單**上  
假設有一個**Field** 的名稱是 &#8220;**Name**&#8221;  
我們便要把 他的**Data Type** 從 **<span style="color: #339966;">NVARCHAR(260)</span>** 轉換成 **<span style="color: #339966;">NVARCHAR(425)</span>**&#8230;  
如果要自己每一個**Table** / **表單**上 都打開來看..那會需要很多時間

如果有看過我之前發的網誌便會知道我們可以嘗試 Query **<span style="color: #339966;">Database.Information_Schema</span>** 來取得資料庫的資訊  
<a title="TSQL Query retrieve all stored procedure from the database – TSQL 找出資料庫內有的Stored procedure" href="http://blog.sharechiwai.com/2013/10/tsql-query-ret…ored-procedure/ " target="_blank">TSQL Query retrieve all stored procedure from the database – TSQL 找出資料庫內有的Stored procedure</a>

要取得那一個Table 有某一個Field 我們都可以用相同的方法的  
E.G.  
這次我們會用到<span style="color: #339966;"><strong>[DatabaseName].information_schema.columns</strong> </span>來取得**Columns** 相關的資訊

解決方法

[sql]  
SELECT *  
FROM ReportServer.information_schema.COLUMNS  
WHERE COLUMN_NAME=&#8217;Name&#8217;  
[/sql]

[<img class="alignnone size-full wp-image-2945" alt="Information_Schema.COLUMNS" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Information_Schema.COLUMNS.jpg?resize=625%2C187" width="625" height="187" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Information_Schema.COLUMNS.jpg)  
Hope you find it useful