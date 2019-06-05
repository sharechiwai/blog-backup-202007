---
id: 2952
title: 'TSQL Backup Database &#8211; 使用 TSQL 來做資料庫備份'
date: 2013-10-07T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2952
permalink: '/2013/10/tsql-backup-database-%e4%bd%bf%e7%94%a8-tsql-%e4%be%86%e5%81%9a%e8%b3%87%e6%96%99%e5%ba%ab%e5%82%99%e4%bb%bd/'
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - TSQL
---
由於不知道公司的**DBA** 怎樣設定公司的**TFS Server的 Database Backup** 的關係&#8230;  
所以為了方便自己去**Backup** 現有的**TFS Database**都要自己用**Script** /**Query** 來建立這個**Database Backup**  
希望不用搞亂他的設定

之前沒有嘗試過**用SQL Script** 來做 **Database Backup**的..  
做了一會兒**Research**之後發現 原來解決方法十分簡單

[SQL]  
BACKUP DATABASE [Database 名稱]  
TO DISK = &#8216;[Database Backup 檔的位置和檔案名.bak]&#8217;  
WITH FORMAT,  
MEDIANAME = &#8216;[Restore database 時所看到的名]&#8217;,  
NAME = &#8216;[Restore database 時所看到的名]&#8217;;  
[/SQL]

我們可以在**SQL Server Management Studio** (**SSMS**)執行以下的Syntax 來實行  
**解決方法**:  
E.G.

[SQL]

BACKUP DATABASE Tfs_DefaultCollection  
TO DISK = &#8216;\\tfs01\Backup\Tfs\_DefaultCollection\_Offline_20131007.Bak&#8217;  
WITH FORMAT,  
MEDIANAME = &#8216;Tfs\_DefaultCollection\_Backup&#8217;,  
NAME = &#8216;Full Backup of Tfs DefaultCollection Offline&#8217;;  
[/SQL]

Hope you find it useful