---
id: 3619
title: SQL Server Keep Track on Log Space
date: 2016-04-12T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3619
permalink: /2016/04/sql-server-keep-track-on-log-space/
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - Transaction Log
---
最近終於有機會 去做一些**Database Mangement** 的任務  
如果有留意之前的Blog都會發現公司很多時候都會有<span style="color: #ff0000;"><strong>Transaction Log Full</strong> </span>這個問題  
所以便想寫一些**schedule** 來**moniter transaction log**什麼時候會用了多小  
還有當有**log shipping**有問題是 也可以predict得到  
[因為**Transaction log**的**used Percentage** 應該都會留在得高位置]  
首先我們要建立一個 **Temp table**去把 之前介紹 取得**Log Space** 資訊輪出的資料暫存在這個Table上

### <a href="http://blog.sharechiwai.com/2013/05/tsql-how-to-get-the-transaction-log-size-mssql/" rel="bookmark">TSQL – How to Get the Transaction Log Size -MSSQL</a> {.entry-title}

<pre>DECLARE @LogSpace TABLE(
DatabaseName VARCHAR(255), 
LogSizeMB DECIMAL(18,2), 
SpaceUsedPercentage DECIMAL(18,2), 
LogStatus VARCHAR(1)

)
</pre>

之後把**Export出來的Log 資訊 暫存在這個Table上**

<pre>INSERT INTO @LogSpace
EXEC('DBCC SQLPERF(logspace)');
</pre>

由於這是一個Demo所以便再Create 一個新的temp table 來儲存這個Log資料  
但是在**這個Table上我加了 DOE (Date Of Entry) 來方便將來分析這些Log什麼時候會開始滿**

<pre>DECLARE @LogSpaceLog TABLE(
DatabaseName VARCHAR(255), 
LogSizeMB DECIMAL(18,2), 
SpaceUsedPercentage DECIMAL(18,2), 
LogStatus VARCHAR(1),
DOE DATETIME DEFAULT GETDATE()

)
</pre>

**加資料加進這個Table上**

<pre>INSERT INTO @LogSpaceLog
(DatabaseName, LogSizeMB, SpaceUsedPercentage, LogStatus)
SELECT DatabaseName, LogSizeMB, SpaceUsedPercentage, LogStatus
FROM @LogSpace
</pre>

**Preview**

<pre>SELECT *
FROM @LogSpaceLog
</pre>

hope you find it useful