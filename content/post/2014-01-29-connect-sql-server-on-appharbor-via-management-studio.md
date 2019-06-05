---
id: 3028
title: Connect SQL Server on Appharbor via Management Studio
date: 2014-01-29T00:00:40+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3028
permalink: /2014/01/connect-sql-server-on-appharbor-via-management-studio/
categories:
  - ASP.Net Tips and Tricks
tags:
  - AppHarbor
---
今天想和大家分享 使用 **AppHarbor** 上的 **SQL Server**的方法  
其實和其他連續雲端的 **Microsoft SQL Server** 差不多的  
可能我太耐沒有學習新的東西..  
所以在找如何在**AppHarbor**上連接 到**Microsoft SQL Server**..也花了一點時間

最後終於找到方法了

大家先選擇你的**Application**  
之後在左手邊的選項上可以找到 你可以做的東西  
選擇&#8221; **Configuration Variable**&#8221;  
之後便會看到所有和這個**Application** 相關係設定變數  
<img class="alignnone" alt="AppHarbor Configuration Variable" src="https://i0.wp.com/farm8.staticflickr.com/7445/12508567234_b6513bd9fa_z.jpg?resize=625%2C292" width="625" height="292" data-recalc-dims="1" />  
只要複製 到文字檔上便可以看到 和SQL Server 上的設定  
E.G.  
Server Name, Database name, username password

E.g.  
**Server**=DBServerName.sqlserver.sequelizer.com;**Database**=ThisIsTheDataBaseName;**User ID**=ThisIsUserName;**Password**=HashedPassword;

之後把資料填上**SQL Server Management Studio** 便可以連接到了

Hope you find it useful