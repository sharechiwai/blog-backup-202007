---
id: 3455
title: 'How to update default language from SQL Server &#8211; 怎樣更改 SQL Server的預設語言'
date: 2015-08-06T00:00:27+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3455
permalink: '/2015/08/how-to-update-default-language-from-sql-server-%e6%80%8e%e6%a8%a3%e6%9b%b4%e6%94%b9-sql-server%e7%9a%84%e9%a0%90%e8%a8%ad%e8%aa%9e%e8%a8%80/'
categories:
  - MSSQL Tips and Tricks
tags:
  - DBA
  - Microsoft SQL Server
  - TSQL
  - TSQL Troubleshooting
---
在安裝**SQL Server** 其間好像沒有地方可以給我們更改 **SQL Server**的預設語言  
所以每當我們建立新的**Database**的時候都會用安裝時預設的語言 E.G. **English** [**US English**]

如果想了解怎樣找到當時使用者在 **SQL Server** 或這個**Database** 上的 語言可以到以下的網誌參考  
<a href="http://blog.sharechiwai.com/2013/05/tsql-get-current-sql-server-language-%e4%bd%bf%e7%94%a8tsql-%e5%8f%96%e5%be%97%e7%8f%be%e5%9c%a8%e7%9a%84sql-server-%e4%bd%bf%e7%94%a8%e4%b8%ad%e7%9a%84%e8%aa%9e%e8%a8%80/" target="_blank">TSQL Get Current SQL Server language – 使用TSQL 取得現在的SQL Server 使用中的語言</a>

當我們需要更新現有**Database的預設語言** 我們會用到這一個 指令

<pre>EXEC sp_configure 'default language', [Language ID] ;
RECONFIGURE
</pre>

但是怎樣可以找到 **SQL Server**上的 **Language ID** 呢  
大家可以執行以下的 **TSQL** 指令

<pre>SELECT *
FROM sys.syslanguages
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3693/19692052204_c8ab360500_z.jpg?resize=625%2C264" alt="SysLanguages on Microsoft SQL Server" width="625" height="264" data-recalc-dims="1" />  
當找到想更新到的 **Language ID** 時大家可以執行 <span style="color: #008000;"><strong>sp_configure</strong></span>去更新 **Database** / 建立新用戶時的預設語言  
在公司需要使用的 預設語言是 **British English**  
所以我要執行的 **TSQL** 是這樣的

&#8212;<span style="color: #008000;"><strong> 23 是British English</strong></span>

<pre>EXEC sp_configure 'default language', 23 ;
-- 之後再執行 Reconfigure 去安裝這個設定
RECONFIGURE
</pre>

Hope you find it useful