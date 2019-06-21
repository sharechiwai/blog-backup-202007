---
id: 3961
title: 'SQL Server Reset / Update user password - SQL Server 如何重設/更新使用者密碼?'
date: 2017-03-28T00:00:44+08:00
author: ShareChiWai
layout: post
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Management
  - SQL Server
---

今日為自己寫一個 **SQL notes**
去記下如何**重設**/**更新** **使用者密碼**[你要**有足夠的使用者權限**才可以的](太久沒有用忘記了User密碼)
**解決方法**:

```sql
ALTER LOGIN [SQL User Name] WITH PASSWORD = '[New Password]';

-- E.G.
ALTER LOGIN sqluser WITH PASSWORD = 'newP@ssW01D';
```

hope you find it useful
