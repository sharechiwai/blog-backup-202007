---
id: 3483
title: 'SQL Server Rebuild Index for all the tables via TSQL &#8211; 如果幫資料庫重建索引所有表單'
date: 2015-09-15T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3483
permalink: '/2015/09/sql-server-rebuild-index-for-all-the-tables-via-tsql-%e5%a6%82%e6%9e%9c%e5%b9%ab%e8%b3%87%e6%96%99%e5%ba%ab%e9%87%8d%e5%bb%ba%e7%b4%a2%e5%bc%95%e6%89%80%e6%9c%89%e8%a1%a8%e5%96%ae/'
categories:
  - .Net Tips And Tricks
---
**Rebuild Index** 相信是 **Database Maintenance 的其中一個重要任務**

**如何 Rebuild All Index for All the table in a database**

**解決方法**十分簡單.

在**SQL Server Management Studio** (**SSMS**) 選擇了**Database**之後  
建立一個新的**Query**

之後我們可以**執行以下的 SQL程式碼**

<pre>DECLARE @TableName varchar(255) 
 
DECLARE TableCursor CURSOR FOR 
 
SELECT table_name FROM information_schema.tables 
 
WHERE table_type = 'base table' 
 

OPEN TableCursor 
 
FETCH NEXT FROM TableCursor INTO @TableName 
 
WHILE @@FETCH_STATUS = 0 
 
BEGIN 
 
DBCC DBREINDEX(@TableName,' ',100) 
 
FETCH NEXT FROM TableCursor INTO @TableName 
 
END 
 
CLOSE TableCursor 
 
DEALLOCATE TableCursor 
</pre>

我們可以參考 **Technet SQL Gallery**  
<a href="https://gallery.technet.microsoft.com/scriptcenter/Script-for-rebuilding-all-8d079754" target="_blank" rel="noopener">https://gallery.technet.microsoft.com/scriptcenter/Script-for-rebuilding-all-8d079754</a>

Hope you find it useful