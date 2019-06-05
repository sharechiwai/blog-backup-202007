---
id: 2524
title: 'TSQL Get Number of Decimal Place Digit &#8211; TSQL 找出數據有多少個小數位是有數值的'
date: 2012-08-08T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2524
permalink: '/2012/08/tsql-get-number-of-decimal-place-digit-tsql-%e6%89%be%e5%87%ba%e6%95%b8%e6%93%9a%e6%9c%89%e5%a4%9a%e5%b0%91%e5%80%8b%e5%b0%8f%e6%95%b8%e4%bd%8d%e6%98%af%e6%9c%89%e6%95%b8%e5%80%bc%e7%9a%84/'
categories:
  - MSSQL Tips and Tricks
  - NuGet
tags:
  - TSQL
---
在之前一個網誌介紹過用TSQL 找出多過2個小數位的record

# <a title="Permalink to Check if TSQL field has contain more than 2 decimal place — TSQL上查看欄位上的有沒有多過2個小數位的資料" href="http://blog.sharechiwai.com/2012/08/check-if-tsql-field-has-contain-more-than-2-decimal-place-tsql%e4%b8%8a%e6%9f%a5%e7%9c%8b%e6%ac%84%e4%bd%8d%e4%b8%8a%e7%9a%84%e6%9c%89%e6%b2%92%e6%9c%89%e5%a4%9a%e9%81%8e2%e5%80%8b%e5%b0%8f/" rel="bookmark">Check if TSQL field has contain more than 2 decimal place — TSQL上查看欄位上的有沒有多過2個小數位的資料 </a>

今天想和大家介紹一個自己寫的功能..  
用來方便找出數據上有多才個小數位是有數值的  
**E.G.**  
**0.1234 = 4個小數位**  
 **0.1200 = 2個小數位**

以下是我**簡單的功能 Get_NoOfDecimalPlaceDigit**

[sql]  
&#8212; =============================================  
&#8212; Author: <ShareChiWai>  
&#8212; Create date: <2012-09-20>  
&#8212; Description: <This function is used to retrive the number of decimal place digit the given value have>  
&#8212; =============================================  
CREATE FUNCTION [dbo].[Get_NoOfDecimalPlaceDigit]  
(  
&#8212;- 首先declare一個parameter做input  
@FieldValue AS DECIMAL(19, 6) = 0  
)  
&#8212;- 輸出的結果是有多少個小數位值..所以是Integer  
RETURNS INT  
AS  
BEGIN  
&#8212;- 很複雜的一個TSQL&#8230; 我用了STR input parameter來把數據轉成了6個小數位的decimal 的string  
&#8212;- 之後再找出小數位&#8230; 再用RIGHT 去取得所有小數位值&#8230;再把他轉做INT  
&#8212;- 用reverse去去除0的餘值&#8230;  
DECLARE @DecimalValue AS INT = CAST(REVERSE(RIGHT(STR(@FieldValue, 20,  
6),  
LEN(STR(@FieldValue,  
20, 6))  
&#8211; CHARINDEX(&#8216;.&#8217;,  
STR(@FieldValue,  
20, 6)))) AS INT)

&#8212;-轉出結果..如果是0的話輸出0.. otherwise輸出數字有多少個數位  
&#8212;- 便找到數據上有多才個小數位是有數值的  
RETURN CASE WHEN @DecimalValue = 0 THEN 0  
ELSE LEN(@DecimalValue)  
END  
END  
[/sql]

**E.G.**

[sql]  
SELECT dbo.Get_NoOfDecimalPlaceDigit(12.35012)  
&#8212;- 結果是5

SELECT dbo.Get_NoOfDecimalPlaceDigit(12.0000)  
&#8212;- 結果是0

[/sql]

Hope you find it useful

Drag and Drop upload file and tag file with filename and correct path&#8230;etc

Media query for different device