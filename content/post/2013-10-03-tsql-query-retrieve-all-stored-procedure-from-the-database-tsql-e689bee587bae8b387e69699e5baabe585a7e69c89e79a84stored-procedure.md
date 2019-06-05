---
id: 2940
title: 'TSQL Query retrieve all stored procedure from the database &#8211; TSQL 找出資料庫內有的Stored procedure'
date: 2013-10-03T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2940
permalink: '/2013/10/tsql-query-retrieve-all-stored-procedure-from-the-database-tsql-%e6%89%be%e5%87%ba%e8%b3%87%e6%96%99%e5%ba%ab%e5%85%a7%e6%9c%89%e7%9a%84stored-procedure/'
categories:
  - MSSQL Tips and Tricks
---
今天朋友問有沒有方法可以找出**Database** 上有多少**Stored Procedure**  
和有沒有辦法找出 有多少**Stored Procedure** 是 某一個**Project** 開首的&#8230;etc  
做了一會兒 **reseach** 找到解決方法十分簡單  
原來我們可以使<span style="color: #339966;"><strong>用[DatabaseName].information_schema.routines</strong> </span>來找出和routines 相關的資訊  
如果要找**Stored Procedure**我們可以用**Where Cause**  
<span style="color: #339966;"><strong>rountine_type = &#8216;PROCEDURE&#8217;</strong></span> 來找**Stored Procedure** 出來

**解決方法**:

[sql]  
SELECT *  
FROM ReportServer.information_schema.routines  
WHERE routine_type = &#8216;PROCEDURE&#8217;  
ORDER BY SPECIFIC_Name  
[/sql]

E.G.  
[<img class="alignnone size-full wp-image-2941" alt="information_Schema.routines" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/information_Schema.routines.jpg?resize=625%2C259" width="625" height="259" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/information_Schema.routines.jpg)  
Hope you find it useful