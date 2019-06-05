---
id: 3961
title: 'SQL Server Reset / Update user password &#8211; SQL Server 如何重設/更新使用者密碼?'
date: 2017-03-28T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3961
permalink: '/2017/03/sql-server-reset-update-user-password-sql-server-%e5%a6%82%e4%bd%95%e9%87%8d%e8%a8%ad%e6%9b%b4%e6%96%b0%e4%bd%bf%e7%94%a8%e8%80%85%e5%af%86%e7%a2%bc/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Management
  - SQL Server
---
今日為自己寫一個 **SQL notes**  
去記下如何**重設**/**更新** **使用者密碼**[你要**有足夠的使用者權限**才可以的]  
(太久沒有用忘記了User密碼)  
**解決方法**:

<pre>ALTER LOGIN [SQL User Name] WITH PASSWORD = '[New Password]';  

-- E.G.
ALTER LOGIN sqluser WITH PASSWORD = 'newP@ssW01D';  
</pre>

hope you find it useful