---
id: 2092
title: 'TSQL Convert Second to Time Hour:Minutes:Second HH:MM:SS &#8211; TSQL 把秒轉成時分秒時間'
date: 2011-09-10T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2092
permalink: '/2011/09/tsql-convert-second-to-time-hourminutessecond-hhmmss-tsql-%e6%8a%8a%e7%a7%92%e8%bd%89%e6%88%90%e6%99%82%e5%88%86%e7%a7%92%e6%99%82%e9%96%93/'
categories:
  - MSSQL Tips and Tricks
tags:
  - MSSQL
  - TSQL
---
今日同事顯示了一個更加方便的方法把 秒轉成時間 格式 **HH:MM:SS** **[時:分:秒**]

比起我數天前的網誌方便和簡短很多  
 <a title="MSSQL Convert Second to Time Hour:Minutes:Second HH:MM:SS – MSSQL 把秒轉成時分秒時間" href="http://blog.sharechiwai.com/2011/09/mssql-convert-second-to-time-hourminutessecond-hhmmss-mssql-%E6%8A%8A%E7%A7%92%E8%BD%89%E6%88%90%E6%99%82%E5%88%86%E7%A7%92%E6%99%82%E9%96%93/" target="_blank">MSSQL Convert Second to Time Hour:Minutes:Second HH:MM:SS – MSSQL 把秒轉成時分秒時間</a>  
以下是這個方法  
這個方法十分聰明  
我們可以用**TSQL**中的**Convert**的功能  
**Convert**中的 **108的格式是 hh:mi:ss**  
更多的 **TSQL**日期時間轉換格式可以參考以下網頁  
 <a title="CAST 和 CONVERT (Transact-SQL)" href="http://msdn.microsoft.com/zh-tw/library/ms187928(v=SQL.105).aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms187928(v=SQL.105).aspx</a>

之後我們可以好好運用 **TSQL** 的**DATEADD** 功能  
加入我們需要轉換的秒數 之後把結果轉換成 **108的格式**

**解決方法**:  
以下是自定的**function**:

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
&#8211;使用DATEADD 這個功能把秒加上..之後使用Convert Varchar的功能轉日期的格式為108 hh:mi:ss  
SET @HHMMSS = CONVERT(varchar, DATEADD(s, @Second, 0), 108)

&#8212; Return the result of the function  
RETURN @HHMMSS

END  
[/sql]

執行方法:

[sql]  
SELECT dbo.ConvertSecondToHHMMSS (3999)  
[/sql]

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e26c7717760146369aa956e40e8af916/renditions/fullsize.jpg?resize=351%2C185" alt="TSQL convert second to HH:MM:SS" width="351" height="185" data-recalc-dims="1" />  
Hope you find it useful