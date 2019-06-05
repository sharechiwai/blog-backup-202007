---
id: 3645
title: 'TSQL Get size of all tables in database &#8211; TSQL 查詢Table佔用了多小空間'
date: 2016-05-01T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3645
permalink: '/2016/05/tsql-get-size-of-all-tables-in-database-tsql-%e6%9f%a5%e8%a9%a2table%e4%bd%94%e7%94%a8%e4%ba%86%e5%a4%9a%e5%b0%8f%e7%a9%ba%e9%96%93/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - DBA
  - TSQL
---
在整理公司的**Database** 其間發現公司的其中一個Database 的 MDF 檔 799GB 大  
之後發現入面有很多用來做Backup的Table  
是Developer 有時貪方便  
便使用 <span style="color: #008000;"><strong>INSERT INTO z_TableName</strong></span>  
來Backup Table 之後便留下了很多的佔有空間的Table 又未必有用 便在這個Database 上

或些有時候有些Table存有很多 舊的Data..又可能不常用  
所以希望找一個Query來 查詢在**Database**上的Table佔有多小空間 和用了多小Row  
有多小空間 **Provision**了 但是沒有用.. 那我們可以考慮使用一些 **TSQL Command**來**Reclaim/釋放** 那些空間

**解決方法**十分簡單  
我們可以使用這個Query便可以了

<pre>SELECT 
    t.NAME AS TableName,
    s.Name AS SchemaName,
    p.rows AS RowCounts,
    SUM(a.total_pages) * 8/ 1024.00 AS TotalSpaceMB, 
    SUM(a.used_pages) * 8 /1024.00AS UsedSpaceMB, 
    (SUM(a.total_pages) - SUM(a.used_pages)) * 8/1024.00 AS UnusedSpaceMB
FROM 
    sys.tables t
INNER JOIN      
    sys.indexes i ON t.OBJECT_ID = i.object_id
INNER JOIN 
    sys.partitions p ON i.object_id = p.OBJECT_ID AND i.index_id = p.index_id
INNER JOIN 
    sys.allocation_units a ON p.partition_id = a.container_id
LEFT OUTER JOIN 
    sys.schemas s ON t.schema_id = s.schema_id
WHERE 
    t.NAME NOT LIKE 'dt%' 
    AND t.is_ms_shipped = 0
    AND i.OBJECT_ID &gt; 255 
GROUP BY 
    t.Name, s.Name, p.Rows
ORDER BY 
    t.Name
</pre>

<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7699/26763478976_8644b38c19_z.jpg?resize=625%2C574" alt="TSQL Show All space used in Database per table" width="625" height="574" data-recalc-dims="1" />  
Hope you find it useful