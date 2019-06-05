---
id: 2532
title: 'TSQL Get the last day of the month &#8211; TSQL 取得這個月最後的一天'
date: 2012-08-10T00:00:04+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2532
permalink: '/2012/08/tsql-get-the-last-day-of-the-month-tsql-%e5%8f%96%e5%be%97%e9%80%99%e5%80%8b%e6%9c%88%e6%9c%80%e5%be%8c%e7%9a%84%e4%b8%80%e5%a4%a9/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
在之前的一個網誌上 和大家介紹了自己寫了一個簡單的功能

# <a title="Permalink to TSQL Get the first day of the month – TSQL 取得這個月的第一天" href="http://blog.sharechiwai.com/2012/08/tsql-get-the-first-day-of-the-month-tsql-%e5%8f%96%e5%be%97%e9%80%99%e5%80%8b%e6%9c%88%e7%9a%84%e7%ac%ac%e4%b8%80%e5%a4%a9/" rel="bookmark">TSQL Get the first day of the month – TSQL 取得這個月的第一天</a>

今天想和大家介紹另一部分  
就是TSQL **取得這個月最後的一天**

**GenerateLastDayOfMonth**

[sql]  
&#8212; =============================================  
&#8212; Author:  
&#8212; Create date:  
&#8212; Description: &#8212; =============================================  
CREATE FUNCTION [dbo].[GenerateLastDayOfMonth]  
(  
&#8212; Add the parameters for the function here  
@TempDate DATETIME =null,  
@MonthInAdvance INT = 0  
)  
RETURNS DATETIME  
AS  
BEGIN  
RETURN DateAdd(day, -1, DateAdd(month, MONTH(@TempDate)-1+@MonthInAdvance, DateAdd(Year, YEAR(@TempDate)-1900, 0)))  
END  
[sql]  
使用方法十分簡單

[sql]  
SELECT dbo.\[GenerateLastDayOfMonth\](GETDATE(),0);  
[/sql]

**輸出結果**:  
2012-08-31 00:00:00.000

[sql]  
SELECT dbo.\[GenerateLastDayOfMonth\](GETDATE(),2);  
[/sql]

**輸出結果**:  
2012-10-31 00:00:00.000

如果你有更好的方法歡迎和大家分享

Hope you find it useful