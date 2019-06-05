---
id: 3622
title: 'SQL Backup failed with exit code: 5240  SQL error code: 0 [SQLSTATE 42000] (Error 50000).  The step failed. &#8211; SQB service did not acknowledge receipt of data (WAIT_TIMEOUT)'
date: 2016-04-15T00:00:30+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3622
permalink: /2016/04/sql-backup-failed-with-exit-code-5240-sql-error-code-0-sqlstate-42000-error-50000-the-step-failed-sqb-service-did-not-acknowledge-receipt-of-data-wait_timeout/
categories:
  - MSSQL Tips and Tricks
tags:
  - RedGate
  - SQL Backup
  - Transaction Log
---
公司同事成日話..公司的 **SQL Back up** / **Log Shipping** 等的 **SQL Job** 成日都<span style="color: #ff0000;"><strong>failed</strong></span>  
好耐都無 **success**過了

最後都是忍不住去看看有什麼問題  
在**SQL Server**的 **Log File Viewer** 上看到以下的 Log Summary  
&#8220;<span style="color: #ff0000;"><strong>SQL Backup failed with exit code: 5240 SQL error code: 0 [SQLSTATE 42000] (Error 50000). The step failed.</strong></span>&#8221;

<pre>Date		12/04/2016 14:00:00
Log		Job History (SQL Backup log shipping job for database ShareChiWaiDB created 28/03/2011 17:24:57)

Step ID		1
Server		SQL_01
Job Name		SQL Backup log shipping job for database ShareChiWaiDB created 28/03/2011 17:24:57
Step Name		execute master..sqlbackup
Duration		00:00:15
Sql Severity	16
Sql Message ID	50000
Operator Emailed	
Operator Net sent	
Operator Paged	
Retries Attempted	0

Message
Executed as user: SQL_01\Administrator. SQL Backup failed with exit code: 5240  SQL error code: 0 [SQLSTATE 42000] (Error 50000).  The step failed.

</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1549/26311639592_c79bb3160a_z.jpg?resize=625%2C242" alt="SQL Server Log File Viewer" width="625" height="242" data-recalc-dims="1" />  
因為知道這個**SQL Job** 是由**RedGate**建立的  
所以便去了**RedGate**的**Software**上看看  
開啟這個**Database node** 時 發現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>SQB service did not acknowledge receipt of data (WAIT_TIMEOUT)</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1500/25801216583_7b934a281a_z.jpg?resize=449%2C281" alt="SQL service did not acknowledge receipt of data (WAIT_TIMEOUT)" width="449" height="281" data-recalc-dims="1" />  
做了一會research 之後發現解決方法十分簡單

只要去了那個**Database Server**的 &#8220;**Administrative Tools**&#8221; -> &#8220;**Service**&#8221; 上重新啟動　**RedGate**的&#8221;**SQL Backup Agent**&#8220;便可以了  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1520/26378063726_c42cc83f52_z.jpg?resize=603%2C481" alt="Administrative Tools -> Services" width="603" height="481" data-recalc-dims="1" /> 

&#8220;**Service**&#8221; 上重新啟動　**RedGate**的&#8221;**SQL Backup Agent**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1626/26403965555_c51220080c_z.jpg?resize=506%2C132" alt="Restart RedGate -> SQL Backup Agent" width="506" height="132" data-recalc-dims="1" />  
Hope you find it useful