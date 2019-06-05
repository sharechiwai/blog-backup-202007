---
id: 3504
title: 'SQL Server TSQL how to View Index Fragmentation &#8211; 如何查詢資料庫的索引碎片 資料'
date: 2015-09-12T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3504
permalink: '/2015/09/sql-server-tsql-how-to-view-index-fragmentation-%e5%a6%82%e4%bd%95%e6%9f%a5%e8%a9%a2%e8%b3%87%e6%96%99%e5%ba%ab%e7%9a%84%e7%b4%a2%e5%bc%95%e7%a2%8e%e7%89%87-%e8%b3%87%e6%96%99/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Best Practices
  - Database Maintenance
  - DBA
  - MSSQL
  - SSMS
---
今天在研究 **Database Performance** / **資料庫效能**時發現..  
原來**Database** 會像我們的硬碟一樣..會出現 **Fragmentation**/碎片 的  
如果**Fragmentation** 越大..  
Database的效能便會越差..  
當然每天的**Database Maintenance plan** 應該是可以解決這些問題的

今天想和大家分享一個**SQL Query** 用來 查詢 **Database Index 的 Fragmentation** 的 **資料庫的索引碎片**

首先我們要選擇想查詢的 **database**  
之後執行以下的**SQL Query**

<pre>SELECT OBJECT_NAME(st.object_id) AS TableName, 
i.name AS IndexName, 
st.index_type_desc,
st.avg_fragmentation_in_percent, 
st.fragment_count, 
st.avg_fragment_size_in_pages, 
st.page_count, 
st.avg_page_space_used_in_percent, 
st.record_count,
 st.index_depth, st.index_level,st.partition_number, 
st.ghost_record_count, 
st.min_record_size_in_bytes, st.max_record_size_in_bytes, st.avg_record_size_in_bytes
FROM  sys.dm_db_index_physical_stats(DB_ID(DB_Name()), NULL, NULL, NULL , 'SAMPLED') as st
JOIN sys.indexes i 
ON st.object_id = i.object_id AND st.index_id = i.index_id
WHERE index_type_desc &lt;> 'HEAP'
</pre>

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/587/20131505214_db3d8b7003_z.jpg?resize=625%2C249" alt="Database Fragmentation " width="625" height="249" data-recalc-dims="1" /> 

之後他便出輸出很多有用的資訊  
我對下面的幾個資訊比較有興趣  
<span style="color: #008000;"><strong>avg_fragmentation_in_percent</strong></span> &#8211; IN\_ROW\_DATA 配置單位中，索引的邏輯片段或是堆積的範圍片段。其值以百分比表示，而且會考量多個檔案

**<span style="color: #008000;">fragment_count</span>** &#8211; IN\_ROW\_DATA 配置單位分葉層級中的片段數目

<span style="color: #008000;"><strong>avg_page_space_used_in_percent</strong></span>  
&#8211; 所有頁面所用之可用資料儲存空間的平均百分比。 如果是索引，則為 IN\_ROW\_DATA 配置單位中 B 型樹狀目錄目前層級的平均數。 如果是堆積，則為 IN\_ROW\_DATA 配置單位中所有資料頁的平均數。

<span style="color: #008000;"><strong>record_count</strong></span>-總記錄數。

有關**Database Index 的 Physical statiic 的資料**.可以參考以下網頁  
<a href="https://msdn.microsoft.com/en-us/library/ms188917.aspx" target="_blank">https://msdn.microsoft.com/en-us/library/ms188917.aspx</a>

<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/656/20754096645_4ff1b9d79c_z.jpg?resize=607%2C640" alt="Index Info" width="607" height="640" data-recalc-dims="1" /> 

Hope you find it useful