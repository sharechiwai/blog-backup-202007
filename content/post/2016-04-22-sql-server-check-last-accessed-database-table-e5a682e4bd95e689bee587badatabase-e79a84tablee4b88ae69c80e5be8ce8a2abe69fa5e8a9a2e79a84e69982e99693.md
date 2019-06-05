---
id: 3636
title: 'SQL Server Check last accessed Database Table &#8211; 如何找出Database 的Table上最後被查詢的時間'
date: 2016-04-22T00:00:15+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3636
permalink: '/2016/04/sql-server-check-last-accessed-database-table-%e5%a6%82%e4%bd%95%e6%89%be%e5%87%badatabase-%e7%9a%84table%e4%b8%8a%e6%9c%80%e5%be%8c%e8%a2%ab%e6%9f%a5%e8%a9%a2%e7%9a%84%e6%99%82%e9%96%93/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - TSQL
---
公司上有很多 **Legacy** / 舊有的Database 由于同事離開始於時沒有好好交代  
所以便有很多在**Database Server**上存在的Database 但是又沒大人知道有沒有任何Application 會連接的

今天想和大家分享一個<span style="color: #3366ff;"><strong>SQL Script</strong></span>有來查詢某一個Database最後一次被就**Query**/**Update**的時間  
解決放法十分簡單

首先我們需要先選擇想查詢的**Database**  
之後我們可以使用 以下的SQL Script 來看看 <span style="color: #008000;"><strong>last_user_seek</strong></span>, <span style="color: #008000;"><strong>last_user_scan</strong></span>, <span style="color: #008000;"><strong>last_user_lookup</strong> </span>的內容  
看看他們的更改時間

<pre>SELECT    OBJECT_NAME(object_id) AS TableName,
last_user_update, last_user_seek, last_user_scan, last_user_lookup
FROM    sys.dm_db_index_usage_stats
WHERE    database_id = DB_ID()

</pre>

<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1645/26434603931_fd6d271f0a_z.jpg?resize=625%2C438" alt="SQL Server check which is the Last Accessed Table " width="625" height="438" data-recalc-dims="1" />  
Hope you find it useful