---
id: 3429
title: 'TSQL &#8211; Check Space used by a tables &#8211; 如何查詢 DataTable佔的 Database空間的大小'
date: 2015-06-05T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3429
permalink: '/2015/06/tsql-check-space-used-by-a-tables-%e5%a6%82%e4%bd%95%e6%9f%a5%e8%a9%a2-datatable%e4%bd%94%e7%9a%84-database%e7%a9%ba%e9%96%93%e7%9a%84%e5%a4%a7%e5%b0%8f/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - DBA
  - TSQL
---
最近開始研究 **Database Maintenance** 的方向  
很多時候都想對公司的**Table**了解多一些  
看看那個**Database Table** **佔的空間比較大**

如果大家想看看在**Database**上不同的**Table**佔了多小空間..  
可以在選擇了**Database**後執行以下的**SQL Query**

<pre>SELECT 
 t.NAME AS TableName,
 i.name AS IndexName,
 SUM(p.rows) AS RowCounts,
 SUM(a.total_pages) AS TotalPages, 
 SUM(a.used_pages) AS UsedPages, 
 SUM(a.data_pages) AS DataPages,
 (SUM(a.total_pages) * 8) / 1024 AS TotalSpaceMB, 
 (SUM(a.used_pages) * 8) / 1024 AS UsedSpaceMB, 
 (SUM(a.data_pages) * 8) / 1024 AS DataSpaceMB
FROM 
 sys.tables t
INNER JOIN  
 sys.indexes i ON t.OBJECT_ID = i.object_id
INNER JOIN 
 sys.partitions p ON i.object_id = p.OBJECT_ID AND i.index_id = p.index_id
INNER JOIN 
 sys.allocation_units a ON p.partition_id = a.container_id
WHERE 
 t.NAME NOT LIKE 'dt%' AND
 i.OBJECT_ID &lt; 255 AND  
 i.index_id >= 1 
GROUP BY 
 t.NAME, i.object_id, i.index_id, i.name 
ORDER BY 
 OBJECT_NAME(i.object_id) 
</pre>

之後他便會出列出 以下的資料&#8230;其實都很有用的  
<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8869/18449546032_bd0f105b24_z.jpg?resize=625%2C428" alt="Table size per Database on Microsoft SQL Server" width="625" height="428" data-recalc-dims="1" />  
**IndexName** = 在Table上有的 Index的名稱  
**RowCounts** = 在這個Table上有多 行  
最主要都是看 Total Space用了多小

之後的網誌會和大家分享怎樣可以 release返一些沒有使用的空間

Hope you find it useful