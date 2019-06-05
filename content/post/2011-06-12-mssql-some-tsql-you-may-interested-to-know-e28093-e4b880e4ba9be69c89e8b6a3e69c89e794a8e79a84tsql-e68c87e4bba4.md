---
id: 1820
title: MSSQL Some TSQL you may interested to Know – 一些有趣/有用的TSQL 指令
date: 2011-06-12T00:00:36+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1820
permalink: '/2011/06/mssql-some-tsql-you-may-interested-to-know-%e2%80%93-%e4%b8%80%e4%ba%9b%e6%9c%89%e8%b6%a3%e6%9c%89%e7%94%a8%e7%9a%84tsql-%e6%8c%87%e4%bb%a4/'
categories:
  - MSSQL Tips and Tricks
---
今天在朋友的網誌上學會了更多檢查 **Microsoft SQL Server**狀況的**TSQL Code**  
感到十分有用..  
希望大家喜歡

用來找出這台**SQL Server 上已經安裝了多小棵CPU**

<pre>SELECT  COUNT(*) AS No_Of_Processor
FROM    sys.dm_os_schedulers
WHERE   status = 'VISIBLE ONLINE'</pre>

用來找出**SQL Server在什麼時候開始運作**

<pre>SELECT
    crdate AS Start_Date_Time_Of_SQL_Server
FROM
     master.dbo.sysdatabases
WHERE
    name = 'tempdb'</pre>

用來**建立新的SQL Log 檔案**

<pre>EXEC sp_cycle_errorlog</pre>

Hope you find it useful

&nbsp;