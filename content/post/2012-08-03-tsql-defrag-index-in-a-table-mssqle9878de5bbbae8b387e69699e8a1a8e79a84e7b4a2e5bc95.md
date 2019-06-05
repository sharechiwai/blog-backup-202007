---
id: 2514
title: 'TSQL Defrag index in a table &#8211;  MSSQL重建資料表的索引'
date: 2012-08-03T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2514
permalink: '/2012/08/tsql-defrag-index-in-a-table-mssql%e9%87%8d%e5%bb%ba%e8%b3%87%e6%96%99%e8%a1%a8%e7%9a%84%e7%b4%a2%e5%bc%95/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
之前和大家介紹過..如何在**TSQL** 上取得 **Database Table上的資料與索引碎片分散的數據**  
<a title="Permalink to Show table fragmentation on TSQL – 如何顯示 MSSQL Table 上有沒有碎片呢?" href="http://blog.sharechiwai.com/2012/08/show-table-fragmentation-on-tsql-%e5%a6%82%e4%bd%95%e9%a1%af%e7%a4%ba-mssql-table-%e4%b8%8a%e6%9c%89%e6%b2%92%e6%9c%89%e7%a2%8e%e7%89%87%e5%91%a2/" rel="bookmark">Show table fragmentation on TSQL – 如何顯示 MSSQL Table 上有沒有碎片呢?</a>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7c32a640b1d140ba9cacdbe8cdb922bd" alt="Show table fragmentation result before rebuild index" width="712" height="278" />  
當**Database Table**上**資料與索引碎片分散很多**的話怎麼辦呢?  
今天想和大家介紹一個十分簡單的解決方法  
就是將Database 的 Table上的**索引重建**/**rebuild index**

我們可以使用以下的**TSQL Command**

[sql]  
DBCC dbreindex(&#8216;Table_Name&#8217;)  
&#8211;E.G.  
DBCC dbreindex(&#8216;ShareChiWai_SampleTable&#8217;)  
&#8211;完成之後會出現以下的output  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
[/sql]

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/57353fa1a56740779a1dc49231d60d55" alt="DBCC execution completed. If DBCC printed error messages, contact your system administrator." width="673" height="108" /> 

執行完這個 **Index Rebuild的Command**之後  
大家可以再次 執行 **DBCC SHOWCONTIG Command**  
看看資料與索引碎片分散的數據

[sql]  
DBCC SHOWCONTIG ("Table name");  
[/sql]

這應該可以解決資料與索引碎片分散的問題的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/6dc574b93dc345cca10d80ecbbc0f867" alt="DBCC ShowContig result after rebuild Index" width="677" height="280" /> 

Hope you find it useful