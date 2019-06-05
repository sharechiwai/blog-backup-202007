---
id: 3866
title: 'MS SQL Notes &#8211; Database Management Scripts'
date: 2017-02-15T06:55:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3866
permalink: /2017/02/ms-sql-notes-database-management/
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - Microsoft SQL Server
  - MSSQL
  - SQL Script
  - TSQL
---
最近有機會去接觸公司的**Database**  
可以幫忙**performance tuning**  
很可惜在之前的公司沒有好好的記下一些有用的script  
今日想和大家分享一些有用的**Database Management script**  
和用來**check Database** 的東西  
以下有兩個網頁  
<https://ola.hallengren.com/>

這個提供了一些**SQL Server Backup, Integrity Check, and Index and Statistics Maintenance**的script/解決建議  
Script 可以在這裡下載  
[https://ola.hallengren.com/scripts/MaintenanceSolution.sql  
](https://ola.hallengren.com/scripts/MaintenanceSolution.sql) [<img class="alignnone size-large wp-image-3867" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?resize=625%2C308" alt="SQL Server Maintenance Solution" width="625" height="308" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?resize=1024%2C505 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?resize=300%2C148 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?resize=768%2C379 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?resize=624%2C308 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065130.png)

而  
<http://whoisactive.com/>  
提供了script來幫助 **Monitor SQL Server**的  
去到網頁入面便可以download之後在 **SQL Server Management Studio**上執行便可以安裝這些script了  
[<img class="alignnone size-large wp-image-3868" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?resize=625%2C245" alt="sp_whoisactives" width="625" height="245" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?resize=1024%2C402 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?resize=300%2C118 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?resize=768%2C302 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?resize=624%2C245 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?w=1250 1250w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png?w=1875 1875w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/snip_20170215065401.png)

有時間再和大家介紹他們的use case

Hope you find it useful