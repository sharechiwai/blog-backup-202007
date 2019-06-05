---
id: 349
title: From MSSQL/TSQL to MYSQL
date: 2009-10-24T03:05:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/10/24/from-mssqltsql-to-mysql
permalink: /2009/10/from-mssqltsql-to-mysql/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4508736668399474707"
categories:
  - MySQL Tips and Tricks
---
<span style="font-family:Verdana;font-size:13px;"></span>

<div style="margin-bottom:0;margin-top:0;">
  Have been working on MSSQL for quite a while. Now I started to work on MySQL. After you got the basic knowledge of SQL. I guess switch from MSSQL to MYSQL should not be too difficult.
</div>

<div style="margin-bottom:0;margin-top:0;">
</div>

<div style="margin-bottom:0;margin-top:0;">
  When I try to wrote some Stored procedure in MYSQL. I find it little bit hard, as the syntax and keywords is a bit different. Therefore I start to drop down some notes about the difficulty i encountered when I using MYSQL.
</div>

<div style="margin-bottom:0;margin-top:0;">
</div>

<div style="margin-bottom:0;margin-top:0;">
  E.g.
</div>

<div style="margin-bottom:0;margin-top:0;">
  You need to ensure you have place semi-colon &#8220;<b>;</b>&#8221; at the end of each of the MySQL statement.
</div>

<div style="margin-bottom:0;margin-top:0;">
  When you declare a variable in Stored procedure you do not need to put &#8220;<b>@</b>&#8221; in front of the variable in MySQL
</div>

<div style="margin-bottom:0;margin-top:0;">
</div>

<div style="margin-bottom:0;margin-top:0;">
  Hope you find it useful too.
</div>