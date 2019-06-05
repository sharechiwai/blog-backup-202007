---
id: 3642
title: 'Microsoft SQL Server Check If Full-Text Search is Installed &#8211; 如何查詢 SQL Server上的 Full Index Search 是否已經安裝'
date: 2016-04-25T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3642
permalink: '/2016/04/microsoft-sql-server-check-if-full-text-search-is-installed-%e5%a6%82%e4%bd%95%e6%9f%a5%e8%a9%a2-sql-server%e4%b8%8a%e7%9a%84-full-index-search-%e6%98%af%e5%90%a6%e5%b7%b2%e7%b6%93%e5%ae%89%e8%a3%9d/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - DBA
  - TSQL
---
最近忙於將公司的 **Database**由舊的**Server Migrate**到新的 **Environment**  
舊的DBA當然很小心地沒有留下任何 Notes 他怎麼設定舊的Database  
所以這次**Migration**有很多東西都要自己摸索

在設定時安裝程式問..要不是安裝 **Full Text Search**..  
我真是不清楚舊的Server有沒有安裝.. 只是知道沒有使用過這個Feature  
做了一會research之後發現  
其實是可以用Query來查詢這些設定的  
我們可以使用以下我**Query**來查詢 **SQL Server**上的 **Full Index Search** 是否已經安裝

<pre>SELECT FULLTEXTSERVICEPROPERTY('IsFullTextInstalled')
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1520/26087546373_8859936ef9_z.jpg?resize=625%2C254" alt="SQL Server Full Text Search Info" width="625" height="254" data-recalc-dims="1" />  
以下的**Query**可以提供更多的資訊

<pre>SELECT * FROM sys.fulltext_catalogs
</pre>

Hope you find it useful