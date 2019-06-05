---
id: 1008
title: 'Generate Timestamp (yyyyMMddhhmmss)in MSSQL &#8212; 在MSSQL 中建立一個像時間戳的值'
date: 2010-11-20T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1008
permalink: /2010/11/generate-timestamp-yyyymmddhhmmssin-mssql-2/
categories:
  - MSSQL Tips and Tricks
---
今天工作上需要在資料庫中的 其中一個Field 上 填上一個 像Timestamp 一樣的 (yyyyMMddhhmmss)格式的 內容..方便大家..可以很容易了解這個資料是什麼時候寫入的&#8230;  
你可能會問入什麼不同DateTime 的GetDate() 放法來實現這個動作&#8230;  
有時候由於我們要輸出資料庫的數據給其他公司&#8230; 如果是直接輸出這些DateTime value到Excel 或CSV&#8230; 由於格式的問題所以可能會令人有點亂&#8230;  
另一個原因是&#8230;如果我們要跟據不同的日期時間來做一些query&#8230; 在MSSQL 中輸入 一個日期和時間去query 一些資料&#8230;在不同的資料庫設定..E.G. 不同Language 設定&#8230; 也可能會給你不同的結果的&#8230;E.G. 01/10/2010 是 2010年10月1日..還是2010年1月10日呢&#8230;這便可能令人更加混亂了 所以早後都是把這個Field 的值變成 (yyyyMMddhhmmss)&#8230;  
感覺有點困難  
如果這是 VB.Net 的話&#8230; 我便可以用**ShareChiWaiLib** 中的 **StringFunc.GetTimeStamp()** 便可以輸出這樣的值&#8230;  
詳情可以參考以下URL  
[http://sharechiwailib.codeplex.com/](http://sharechiwailib.codeplex.com/ "ShareChiWaiLib")

如果想把這個值設定成一個Column/Field 的Default value&#8230;  
這便要動動腦筋了&#8230;

最後找到用UDF [User Define Function] 的方法來實現

Here it is the UDF that i created for MSSQL.

[sql]  
CREATE FUNCTION [dbo].[GenerateBatchNum]  
(  
&#8212; Add the parameters for the function here  
@TempDateTime DATETIME  
)  
RETURNS VARCHAR(20)  
AS  
BEGIN  
&#8212; Declare the return variable here  
DECLARE @BatchNum VARCHAR(20)

SET @BatchNum = CONVERT(VARCHAR(20),@TempDateTime,20)  
SET @BatchNum=REPLACE(@BatchNum,&#8217;:&#8217;,&#8221;)  
SET @BatchNum=REPLACE(@BatchNum,&#8217; &#8216;,&#8221;)  
SET @BatchNum=REPLACE(@BatchNum,&#8217;-&#8216;,&#8221;)

&#8212; Return the result of the function  
RETURN @BatchNum

END  
[/sql]

**執得方法**十分簡單:

[sql]  
SELECT dbo.GenerateBatchNum(GETDATE())  
[/sql]

如果大家有更好的方法/或者發現我這些Code 有問題的話..希望你們可以分享一下 =)

Happy programming