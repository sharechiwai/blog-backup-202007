---
id: 3908
title: WhoIsActive for Azure
date: 2017-03-10T00:00:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3908
permalink: /2017/03/whoisactive-for-azure/
categories:
  - MSSQL Tips and Tricks
tags:
  - Azure
  - Azure Database
  - Microsoft SQL Server
  - MSSQL
  - WhoIsActive
---
之前和大家分享了一些 十分有用的**SQL Script**  
用來 **Monitor / **檢查 **SQL Server **  
<a href="http://blog.sharechiwai.com/2017/02/ms-sql-notes-database-management/" rel="bookmark">MS SQL Notes – Database Management Scripts</a>  
今日同事想查詢公司某一個Database 有什麼query 正在執行

在這個情況..使用**sp_whoisactive** 這個**script　**便最適合了  
可以看到有什麼query在執行..和已經執行多久  
可惜嘗試在 **Azure**的**database** 安裝時出現了些問題  
應該是**permission**的問題..不能在**master**上執行

做了一會research之後發現..原來他有一個給Azure 用的WhoIsActive script  
只需要在每一個**Azure** 上的**Database** 執行便可以了

詳情可以考以下Blog Post

<http://sqlblog.com/blogs/adam_machanic/archive/2016/04/14/sp-whoisactive-for-azure-sql-database-attempt-2.aspx>

或到以下網址下載這個**WhoIsActive script**  
<http://sqlblog.com/blogs/adam_machanic/attachment/61064.ashx>

Hope you find it useful