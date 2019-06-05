---
id: 822
title: 'MSSQL Get Last Inserted Index (last auto-incremental Number) &#8212;在MSSQL 的預設程序中取出自動遞增數值'
date: 2010-10-27T00:00:20+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=822
permalink: /2010/10/mssql-get-last-inserted-index/
categories:
  - MSSQL Tips and Tricks
---
<div id="_mcePaste">
  <span style="line-height: 24px; font-size: 16px;">今日所寫的網誌主要是用來提醒自己在<strong>MSSQL </strong>中怎樣可以取得 <strong>Auto-Increment Number</strong>因為每當要建立一個新的<strong>Stored Procedure </strong> 的 Insert 時..我常常會忘記怎麼在MSSQL 中取得 這個剛剛寫入資料的<strong>Auto-Increment Number</strong>&#8230;又要到網上找資料..或在之前寫下來的<strong>Stored procedure</strong> 上找回這一段Code</span>
</div>

其實這段SQL Code 十分簡單&#8230;但總是忘了怎樣寫的&#8230;  
<span style="color: #008000;"><strong> IF (@@ERROR = 0) SELECT @ID= SCOPE_IDENTITY()</strong></span>

<span style="color: #008000;"><strong>IF (@@ERROR = 0)&#8211;</strong></span> 是用來檢查在之前執行的SQL 語法有沒有錯誤  
如果沒有的**@@ERROR** 的數值會等如 0  
之後我會便可以用  **SCOPE_IDENTITY()** 來取得剛剛 Insert 的資料Record  
的Auto-increment Number 了

E.G.

 <span style="color: #008000;">DECLARE @ID INT</span>

<span style="color: #008000;">INSERT INTO TABLE1<br /> (Field1, Field2)<br /> VALUES<br /> (&#8216;Field1&#8217;, &#8216;Field2&#8217;)</span>

<span style="color: #008000;">IF (@@ERROR = 0) SELECT @ID= SCOPE_IDENTITY()</span>

Hope you find it useful

<div>
</div>