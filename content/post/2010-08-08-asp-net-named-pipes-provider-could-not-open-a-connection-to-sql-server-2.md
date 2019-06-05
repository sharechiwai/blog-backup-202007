---
id: 490
title: 'ASP.Net &#8212; Named Pipes Provider: Could not open a connection to SQL Server [2]'
date: 2010-08-08T08:08:31+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=490
permalink: /2010/08/asp-net-named-pipes-provider-could-not-open-a-connection-to-sql-server-2/
jabber_published:
  - "1282498332"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282653842";}";'
tagazine-media:
  - 's:192:"a:7:{s:7:"primary";s:0:"";s:6:"images";a:0:{}s:6:"videos";a:0:{}s:11:"image_count";s:1:"0";s:6:"author";s:8:"15700447";s:7:"blog_id";s:8:"15180134";s:9:"mod_stamp";s:19:"2010-08-22 17:32:11";}";'
categories:
  - ASP.Net Tips and Tricks
  - Microsoft
  - MSSQL Tips and Tricks
---
這個週末..公司又升級資料庫, 由**Microsoft SQL 2000** 升級到 **Microsoft SQL 2008**  
之後公司有位朋友Email 我叫我幫忙測試一下升級後的公司的網站有沒有什麼功能壞了

當我用**Visual Studio** 進行**Debug** 時  
發現有一個功能是用要執行 一個**Stored Procedure**  
而這條**Stored Procedure** 是會用到**Linked Server** 和**View** 的複雜**Query**  
出現問題..

由於這個功能在SQL2000 時使用時沒有問題的  
所以想信不是程式上的錯誤&#8230;  
而是SQL Server或一些設定的錯誤  
<span style="color: #ff0000;"><strong>Named Pipes Provider: Could not open a connection to SQL Server [2]</strong></span>

但是從**SQL Server Management Studio** 執行這個 Stored Procedure 是沒有問題的&#8230;  
真是一個挑戰&#8230;

由於自己沒有權限可以用sa 來嘗試從新設定這個**Server** 所以為有慢慢想想有什麼地方有機會有問題&#8230;  
到最後發現..這有可能是**View**&#8230; 因為之前嘗試過, 原本的**Table**加多了行或改了**Column** 久後  
**View** 不能自動更新到最新的**Table Defination**&#8230;  
所以我便嘗試 重新建立這個**View**

結果..真的是解決了這個問題

Hope you find it useful