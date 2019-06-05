---
id: 3030
title: 't-sql check identity_insert status &#8211; TSQL 檢查identity_insert的狀況'
date: 2014-01-30T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3030
permalink: '/2014/01/t-sql-check-identity_insert-status-tsql-%e6%aa%a2%e6%9f%a5identity_insert%e7%9a%84%e7%8b%80%e6%b3%81/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今天公司有一個程式有需要做一個**Data Refresh**的功能..  
把資料從 一個**Database Transfer** 到另一個**Database**上

如果你的**Table**/**表單**上有 **Identity**的 **Field** 的話

<img class="alignnone" alt="Table with Identity field" src="https://i2.wp.com/farm8.staticflickr.com/7402/12526605544_4aa7da247b_z.jpg?resize=625%2C470" width="625" height="470" data-recalc-dims="1" />  
當你嘗試把 資料加進這個**Identify Field**上時 便會出現以下的錯誤信息

<img class="alignnone" alt="Cannot insert explicit value for identity column in table 'foods_tbl' when IDENTITY_INSERT is set to OFF." src="https://i1.wp.com/farm3.staticflickr.com/2805/12526116055_f1a197ccc3_z.jpg?resize=625%2C136" width="625" height="136" data-recalc-dims="1" /> 

所以如果你想把資料行一個**Table**轉到另一個 **Mirror** 出來的**Table**..  
又想把舊的ID 加進**Mirror** 的 **Table** 上時 便先要停用 **Mirror** 出來的**Table**上的**Identity field 的屬性**

為了方便同事檢查看看要**Transfer**的資料的**Table**上的

[sql]  
select is_identity  
from sys.columns  
where object\_id = OBJECT\_ID([&#8216;表單名稱/Table Name&#8217;]) and name = [&#8216;Field name&#8217;]  
[/sql]

**E.g.**  
<img class="alignnone" alt="Query to check if the field is the Identity field" src="https://i1.wp.com/farm3.staticflickr.com/2879/12526605554_503e9b471d_z.jpg?resize=616%2C185" width="616" height="185" data-recalc-dims="1" /> 

[sql]  
select is_identity  
from sys.columns  
where object\_id = OBJECT\_ID(&#8216;foods_tbl&#8217;) and name = &#8216;foodId&#8217;  
[/sql]

Hope you find it useful