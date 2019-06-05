---
id: 3640
title: 'TSQL Get Index Size Per Table &#8211; 如何使用TSQL 來查詢每一個Table上 每一個Index 佔用的空間大小'
date: 2016-04-23T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3640
permalink: '/2016/04/tsql-get-index-size-per-table-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8tsql-%e4%be%86%e6%9f%a5%e8%a9%a2%e6%af%8f%e4%b8%80%e5%80%8btable%e4%b8%8a-%e6%af%8f%e4%b8%80%e5%80%8bindex-%e4%bd%94%e7%94%a8/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - DBA
  - TSQL
---
今天想和大家分享**如何使用TSQL 來查詢每一個Table上 每一個Index 佔用的空間大小**  
這個可以令大家明白**Database** 的空間有多小放在Index上  
明白更多..應該有幫助吧

**解決方法**  
我們可以使用以下的**Query** 來查詢 每一個**Table**上 每一個**Index** 佔用的空間大小

<pre>SELECT
OBJECT_NAME(i.OBJECT_ID) AS TableName,
i.name AS IndexName,
i.index_id AS IndexID,
8 * SUM(a.used_pages) AS 'Indexsize(KB)',
8 * SUM(a.used_pages) / 1024.00 AS 'Indexsize(MB)'
FROM sys.indexes AS i
JOIN sys.partitions AS p ON p.OBJECT_ID = i.OBJECT_ID AND p.index_id = i.index_id
JOIN sys.allocation_units AS a ON a.container_id = p.partition_id
GROUP BY i.OBJECT_ID,i.index_id,i.name
ORDER BY OBJECT_NAME(i.OBJECT_ID),i.index_id
</pre>

<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1697/26664529406_144ddb9328_z.jpg?resize=625%2C448" alt="TSQL Get Individual Index Size" width="625" height="448" data-recalc-dims="1" /> Hope you find it useful