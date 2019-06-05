---
id: 789
title: 'Copy Database from SQL2008R2 to SQL2008   &#8212; 把SQL2008R2 資料庫 複製到 SQL2008 上'
date: 2010-10-18T00:00:20+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=789
permalink: '/2010/10/copy-database-from-sql2008r2-to-sql2008-%e6%8a%8asql2008r2-%e8%b3%87%e6%96%99%e5%ba%ab-%e8%a4%87%e8%a3%bd%e5%88%b0-sql2008-%e4%b8%8a/'
categories:
  - MSSQL Tips and Tricks
---
<span style="font-size: 13px; line-height: 19px;">有很多朋友問..怎樣才可以把 <strong>SQL2008R2 </strong>上的資料庫回復到 <strong>SQL2008</strong>上..<br /> </span><span style="font-size: 13px; line-height: 19px;">今日終於難到我了&#8230;<br /> 我們要把在<strong>SQL2008R2 </strong>上的<strong>Team Foundation Server</strong> 複製到<strong>SQL 2008</strong>..<br /> </span><span style="font-size: 13px; line-height: 19px;">很可惜&#8230;最後也做不到&#8230;<br /> </span><span style="font-size: 13px; line-height: 19px;">因為有些<strong>Stored Procedure</strong> 不是用 SQL 寫的&#8230;所以到最後也做不到&#8230;<br /> </span><span style="font-size: 13px; line-height: 19px;">但我測試過.. 我們可以用SSIS 來把 <strong>SQL2008R2 </strong>的資料複製到 <strong>SQL2008</strong> 上<br /> </span><span style="font-size: 13px; line-height: 19px;">詳情可以參考以下網址&#8230;我之前寫的 <strong>SQL2008 複製SQL Object 由一個SERVER 到另一個 SERVER</strong></span>

<div id="_mcePaste">
  <a href="http://blog.sharechiwai.com/2010/05/sql2008-copy-sql-object-from-one-database-to-the-other-sql2008-%E8%A4%87%E8%A3%BDsql-object-%E7%94%B1%E4%B8%80%E5%80%8Bserver-%E5%88%B0%E5%8F%A6%E4%B8%80%E5%80%8B-server/">SQL2008 Copy SQL Object from one database to the other— SQL2008 複製SQL Object 由一個SERVER 到另一個 SERVER</a>
</div>

<div id="_mcePaste">
  Hope you find it useful.
</div>