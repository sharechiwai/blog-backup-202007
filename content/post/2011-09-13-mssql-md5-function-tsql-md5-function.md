---
id: 2097
title: 'MSSQL MD5 function &#8211;  TSQL MD5 Function'
date: 2011-09-13T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2097
permalink: /2011/09/mssql-md5-function-tsql-md5-function/
categories:
  - MSSQL Tips and Tricks
---
今天想為自己建立個一個資料上加入一個**MD5** 的Field  
主要是用來把資料儲存得比較安全的  
回想之前用**MySQL** 有一個方法十分簡單..  
只要用

[sql]  
SELECT MD5(&#8216;想MD5的文字&#8217;)  
[/sql]

便可以  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e150f712eb5845b5b65b398503243e5c/renditions/fullsize.jpg?resize=565%2C155" alt="MySQL MD5 Function Demo" width="565" height="155" data-recalc-dims="1" />  
誰不知..**MSSQL** 沒有一個Built-in的功能來做MD5 encrypt文字這個動作  
之後做了一段資料research後便自己做了一個MD5 的功能給MSSQL用了  
這個function 用了 **HashBytes** 把文字轉成**Hash Bytes  
** 之後用 <span style="color: #008000;"><strong>sys.fn_sqlvarbasetostr</strong></span> 把 **Bytes**轉成文字

詳情可以參考以下URL  
<a title="HashBytes (Transact-SQL)" href="http://msdn.microsoft.com/zh-tw/library/ms174415.aspx" target="_blank">HashBytes (Transact-SQL)</a>

[sql]  
&#8212; Author: [Share Chi Wai]  
&#8212; Create date: [2011-09-22]  
&#8212; Description: [This function is used to generate MD5 value of the Input String]  
&#8212; =============================================  
CREATE FUNCTION [dbo].[GenerateMD5Value]  
(  
&#8212; Add the parameters for the function here  
@ValueToEncrypt VARCHAR(500) =&#8221;  
)  
RETURNS VARCHAR(32)  
AS  
BEGIN  
&#8212; Declare the return variable here  
DECLARE @MD5String VARCHAR(50)

&#8212; Add the T-SQL statements to compute the return value here  
SET @MD5String = RIGHT(sys.fn_sqlvarbasetostr(HashBytes(&#8216;MD5&#8217;, @ValueToEncrypt)),32)

&#8212; Return the result of the function  
RETURN @MD5String

END  
[/sql]

我們可以用以下方法執行這個功能

[sql]  
SELECT dbo.GenerateMD5Value(&#8216;Share Chi Wai&#8217;) AS [MD5 String]  
[/sql]

<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e150f712eb5845b5b65b398503243e5c/renditions/fullsize.jpg?resize=565%2C155" alt="TSQL MD5 Function Demo" width="565" height="155" data-recalc-dims="1" /> 

Hope you find it useful