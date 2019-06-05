---
id: 3579
title: 'TSQL Case Sensitive Query &#8211; TSQL 如何寫一條Query可以做一個Case Sensitive match'
date: 2016-02-03T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3579
permalink: '/2016/02/tsql-case-sensitive-query-tsql-%e5%a6%82%e4%bd%95%e5%af%ab%e4%b8%80%e6%a2%9dquery%e5%8f%af%e4%bb%a5%e5%81%9a%e4%b8%80%e5%80%8bcase-sensitive-match/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今日公司有一個程式出現了一個問題  
內容大概是這樣的 &#8220;<span style="color: #ff0000;"><strong>Incorrect syntax near the keyword &#8216;and&#8217;</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1655/24661834910_ec19e540a2_z.jpg?resize=238%2C52" alt="TSQL Incorrect syntax near the keyword" width="238" height="52" data-recalc-dims="1" />  
程式是用來執行一些使用者寫個SQL&#8230;  
我們這個程式當作 **Data Integrity Checker** 吧  
誰不知有使用者在更新這個Table上的 **SQL** 寫了一些有**Syntax Error**的  
**SQL Query** 沒有檢查便儲存了  
嘗試使用Query去找出那些**SQL Query**有 **&#8216;and&#8217;**這個字  
但是由於之前**設定 Database** 時設定了 **TSQL 是 Case Insensitive的關係**  
所以便出現了很多 有 **And**的 record出現 E.G. **&#8216;AND&#8217;**, **&#8216;And&#8217;**, **&#8216;and&#8217;** 等等

那麼怎樣可以寫一條**Query**可以做一個**Case Sensitive match** 呢  
做了一會research之後發現 原來解決方法十分簡單

**解決方法**:  
我們只需要 在 **WHERE Clause**上 要比較的 Field上使用**COLLATE Latin1\_General\_CS_AS** **[一個Case Sensitive的 collation**/ **排序規則**] 便可  
E.G.

<pre>SELECT *
FROM DataIntegrityTable
WHERE IntegritySQL LIKE '%and%' COLLATE Latin1_General_CS_AS
</pre>

Hope you find it useful