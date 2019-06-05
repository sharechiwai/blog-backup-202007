---
id: 3128
title: 'TSQL Get Number Of Records Deleted/Updated/Inserted &#8211; 在TSQL 上 如何知道之前INSERT/UPDATE/DELETE 了多少的資料'
date: 2014-04-10T00:00:58+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3128
permalink: '/2014/04/tsql-get-number-of-records-deletedupdatedinserted-%e5%9c%a8tsql-%e4%b8%8a-%e5%a6%82%e4%bd%95%e7%9f%a5%e9%81%93%e4%b9%8b%e5%89%8dinsertupdatedelete-%e4%ba%86%e5%a4%9a%e5%b0%91%e7%9a%84%e8%b3%87/'
categories:
  - MSSQL Tips and Tricks
---
在**TSQL** 上 如何知道之前**INSERT**/**UPDATE**/**DELETE** 了多少的資料

**解決方法**十分簡單  
我們只要在**TSQL**上加入 <span style="color: #008000;"><strong>NOCOUNT OFF</strong></span>  
來令到Server顯示執行TSQL 後有多少資料被影響  
之後使<span style="color: #008000;"><strong>@@ROWCOUNT</strong></span>

這個變數來取得有多少行資料被影響

**E.G.**

[SQL]  
SET NOCOUNT OFF

DELETE FROM Table_Name  
WHERE Field= &#8216;value&#8217;

SELECT @@ROWCOUNT

[/SQL]

Hope you find it useful