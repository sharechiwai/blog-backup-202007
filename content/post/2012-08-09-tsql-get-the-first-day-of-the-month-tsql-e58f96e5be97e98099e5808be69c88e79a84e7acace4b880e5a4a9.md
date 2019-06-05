---
id: 2528
title: 'TSQL Get the first day of the month &#8211; TSQL 取得這個月的第一天'
date: 2012-08-09T00:00:29+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2528
permalink: '/2012/08/tsql-get-the-first-day-of-the-month-tsql-%e5%8f%96%e5%be%97%e9%80%99%e5%80%8b%e6%9c%88%e7%9a%84%e7%ac%ac%e4%b8%80%e5%a4%a9/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今天需要寫一個功能找出被輸入的月份的第一天和最後一天是什麼日子  
原來解決方法十分簡單  
我寫了一個**TSQL** 的功能 用來方便自己找出來

我取他的名字為 **GenerateFirstDayOfMonth**

[sql]  
&#8212; =============================================  
&#8212; Author: <ShareChiWai>  
&#8212; Create date: <2012-08-23>  
&#8212; Description: <This function is used to retrieve the first day of the month>  
&#8212; =============================================  
CREATE FUNCTION [dbo].[GenerateFirstDayOfMonth]  
(  
&#8212;- 用來設定開始的月份和年份  
@TempDate DATETIME =null,  
&#8212;- 這個變用來給Offset 大家可以用來找出數個月前或後的 First date of the mont  
@MonthInAdvance INT = 0  
)  
RETURNS DATETIME  
AS  
BEGIN  
&#8212; Return the result of the function  
RETURN DateAdd(day, 0, DateAdd(month, MONTH(@TempDate)-1+@MonthInAdvance, DateAdd(Year, YEAR(@TempDate)-1900, 0)))

END  
[/sql]

**使用方法**十分簡單

[sql]  
SELECT dbo.\[GenerateFirstDayOfMonth\](GETDATE(),0);  
[/sql]

**輸出的結果**會是:  
2012-08-01 00:00:00.000

[sql]  
SELECT dbo.\[GenerateFirstDayOfMonth\](GETDATE(),2);  
[/sql]

**輸出的結果**會是:  
2012-10-01 00:00:00.000

如果你有更好的方法歡迎和大家分享

有興趣的朋友可以按下以下網址參考Part 2 TSQL **取得這個月最後的一天**

# <a title="Permalink to TSQL Get the last day of the month – TSQL 取得這個月最後的一天" href="http://blog.sharechiwai.com/2012/08/tsql-get-the-last-day-of-the-month-tsql-%e5%8f%96%e5%be%97%e9%80%99%e5%80%8b%e6%9c%88%e6%9c%80%e5%be%8c%e7%9a%84%e4%b8%80%e5%a4%a9/" rel="bookmark">TSQL Get the last day of the month – TSQL 取得這個月最後的一天 </a>

Hope you find it useful