---
id: 3423
title: 'MSSQL How to Check Log Size and Log Space used &#8211; 在SQL Server上如何查詢MSSQL Server Database的 Log Size 和用了多小空間呢?'
date: 2015-06-02T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3423
permalink: '/2015/06/mssql-how-to-check-log-size-and-log-space-used-%e5%9c%a8sql-server%e4%b8%8a%e5%a6%82%e4%bd%95%e6%9f%a5%e8%a9%a2mssql-server-database%e7%9a%84-log-size-%e5%92%8c%e7%94%a8%e4%ba%86%e5%a4%9a%e5%b0%8f/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Transaction Log
---
最近公司的**Database** 常常投訴<span style="color: #ff0000;"><strong> Transaction Log is full</strong></span>  
那麼怎樣可以知道 **MSSQL Server Database**的 Log Size 和用了多小空間呢?  
我們可以執行以下的SQL 來查詢

<pre>DBCC SQLPERF(logspace)
</pre>

執行之後他會列出在這個**SQL Server Instance**上的**Database Log Size**有用了多小 **%  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7762/18159803918_94aa2db4a4_z.jpg?resize=625%2C244" alt="MSSQL Check Transaction log size" width="625" height="244" data-recalc-dims="1" />  
** 

我們便可以知道是不是真的欠缺空間了 還是一些設定可以解的問題  
[最後發現是公司的**Database maintenance plan**出現問題而造成的 **Transaction Log is full**]

Hope you find it useful