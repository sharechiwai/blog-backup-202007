---
id: 1786
title: 'Microsoft SQL / TSQL Check if Table Exist &#8211; TSQL 檢查Table 是否存在'
date: 2011-06-03T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1786
permalink: '/2011/06/microsoft-sql-tsql-check-if-table-exist-tsql-%e6%aa%a2%e6%9f%a5table-%e6%98%af%e5%90%a6%e5%ad%98%e5%9c%a8/'
categories:
  - MSSQL Tips and Tricks
---
最近終於有時間去Review 自己所寫的一個程式..  
需要計設一個功能方便使用者去**Backup 一個Database Table**.  
由於使用者未必懂得 **TSQL** 的關係  
所以我們便要嘗試做到更 **User Friendly**  
這出現了一些難題&#8230;  
其中一個是  
我們需要檢查一下資料庫上.. 使用者嘗試Backup 到的Table是不是一早已經存在

如果已經存在的話要顯示給使用者&#8230;讓他們可以使用其他**Table name**

**解決方法十分簡單**

我們可以寫一個**TSQL Query**來檢查Table存不存在這個資料庫上  
使用 **INFORMATION_SCHEMA.TABLES** 來檢查Table 相關資料  
[sql]  
DECLARE @Table\_Name NVARCHAR(200) = &#8216;ShareChiWai\_Table&#8217;  
SELECT * FROM INFORMATION_SCHEMA.TABLES  
WHERE TABLE\_NAME =@Table\_Name  
[/sql]

**存在的話結果如下  
[<img class="alignnone" title="Table Already Exist" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05a0959615a742f799761e89caf70eab/renditions/fullsize.jpg?resize=487%2C79" alt="" width="487" height="79" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05a0959615a742f799761e89caf70eab/renditions/fullsize.jpg)** 

**不存在的話結果如下  
[<img class="alignnone" title="Table does not exist" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d68009028f8b42ee974cd09b68926a31/renditions/fullsize.jpg?resize=445%2C130" alt="" width="445" height="130" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d68009028f8b42ee974cd09b68926a31/renditions/fullsize.jpg)** 

Hope you find it useful