---
id: 2089
title: 'MSSQL Convert Second to Time Hour:Minutes:Second HH:MM:SS &#8211; MSSQL 把秒轉成時分秒時間'
date: 2011-09-07T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2089
permalink: '/2011/09/mssql-convert-second-to-time-hourminutessecond-hhmmss-mssql-%e6%8a%8a%e7%a7%92%e8%bd%89%e6%88%90%e6%99%82%e5%88%86%e7%a7%92%e6%99%82%e9%96%93/'
categories:
  - MSSQL Tips and Tricks
tags:
  - MSSQL
  - TSQL
---
公司給客戶的網頁上..  
有一些資料是用秒來儲存的.  
但是為了方便用戶瀏覽的關係..我們便耐要把資料轉換成 時:分:秒 **HH:MM:SS**  
來顯示給用戶看..

由於自己不太熟識**ASP.net MVC**的關係..  
所以不太懂怎樣用**WebGrid**的來顯示時:分:秒

所以我便決定在取資料時做一個資料轉換..  
怎樣可以在資料庫把秒轉換成時間

大家可以用以下的方法

**解決方法**:  
寫一個**function** 把時間轉換便可以了  
可以用一個簡單的方程式來轉換..  
十分簡單:

[sql]  
&#8212; =============================================  
&#8212; Author: [Share Chi Wai]  
&#8212; Create date: [2011-09-07]  
&#8212; Description: [This function is used to convert Second to Time HH:MM:SS]  
&#8212; =============================================  
CREATE FUNCTION [dbo].[ConvertSecondToHHMMSS]  
(  
&#8212; Add the parameters for the function here  
@Second INT =0  
)  
RETURNS VARCHAR(15)  
AS  
BEGIN  
&#8212; Declare the return variable here  
DECLARE @HHMMSS VARCHAR(10)

&#8212; Add the T-SQL statements to compute the return value here  
DECLARE @HH VARCHAR(5)  
DECLARE @MM VARCHAR(2)  
DECLARE @SS VARCHAR(2)

IF LEN((@Second / 3600))<2  
BEGIN  
&#8211;當時間小於雙隻數時..加上一個0  
SET @HH = RIGHT(&#8216;0&#8217;+Convert(VARCHAR(5),(@Second / 3600)),2)  
END  
ELSE  
BEGIN  
&#8211;取時  
SET @HH = Convert(VARCHAR(5),(@Second / 3600))  
END

&#8211;取分  
SET @MM = RIGHT(&#8216;0&#8217;+Convert(VARCHAR(3),(@Second % 3600)/60),2)  
&#8211;取秒  
SET @SS = RIGHT(&#8216;0&#8217;+Convert(VARCHAR(3),@Second % 60),2)  
&#8211;把時/分/秒 轉成正常格式  
SET @HHMMSS= @HH +&#8217;:&#8217; +@MM +&#8217;:&#8217;+ @SS

&#8212; Return the result of the function  
RETURN @HHMMSS

END  
GO  
[/sql]

我們可以用以下方法執行這個功能

[sql]  
SELECT dbo.ConvertSecondToHHMMSS (123)  
[/sql]

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3e4dcb78a6614152868dc736cb2b1fb6/renditions/fullsize.jpg?resize=367%2C191" alt="tsql convert second to HH:MM:SS" width="367" height="191" data-recalc-dims="1" />  
Hope you find it useful