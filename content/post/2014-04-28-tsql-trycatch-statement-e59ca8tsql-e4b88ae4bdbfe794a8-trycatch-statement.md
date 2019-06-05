---
id: 3157
title: 'TSQL TRY/CATCH Statement  &#8211; 在TSQL 上使用 TRY/CATCH Statement'
date: 2014-04-28T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3157
permalink: '/2014/04/tsql-trycatch-statement-%e5%9c%a8tsql-%e4%b8%8a%e4%bd%bf%e7%94%a8-trycatch-statement/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
原來**TSQL** 也有**Try and Catch Block** 的  
今天需要升級同事的一個程式..  
由於這個同事已經不在公司..  
而我們又沒有信心我們的更新的**SQL Query** 不會出錯  
[因為數據是Third Party Provider給我們的&#8230;  
不知道他們的數據會不會Break我們的**TSQL**]  
所以便做了一些Research 看看有沒有一些安全方法..  
可以當**SQL Statement** 出現錯誤時..  
這個**Stored Procedure** 會自動把錯誤信息加進另一個**Table**上.  
我們只需要檢查這個Table便可以知道我們的**SQL Statement** / **Stored Procedure**有沒有出錯了

做完Research 之後發現原來我們可以在**TSQL** 上使用 **Try and Catch Statment** 的  
**E.G.**

[sql]  
BEGIN TRY  
&#8212; SQL Statement  
END TRY  
BEGIN CATCH

&#8212; 顯示錯誤信息.. 在其他Programming 一樣  
SELECT  
ERROR_NUMBER() AS ErrorNumber  
,ERROR_SEVERITY() AS ErrorSeverity  
,ERROR_STATE() AS ErrorState  
,ERROR_PROCEDURE() AS ErrorProcedure  
,ERROR_LINE() AS ErrorLine  
,ERROR_MESSAGE() AS ErrorMessage;

END CATCH  
[/sql]

**擷取錯誤資訊**  
在 **CATCH** 區塊的範圍內，下列系統函數可用來取得造成執行 CATCH 區塊之錯誤的相關資訊：

  * **ERROR_NUMBER()** 會傳回錯誤碼。
  * **ERROR_SEVERITY()** 會傳回嚴重性。
  * **ERROR_STATE()** 會傳回錯誤狀態碼。
  * **ERROR_PROCEDURE()** 會傳回發生錯誤的預存程序或觸發程序的名稱。
  * **ERROR_LINE()** 會傳回常式內造成錯誤的行號。
  * **ERROR_MESSAGE()** 會傳回錯誤訊息的完整文字。 文字包括提供給任何可替代參數的值，例如，長度、物件名稱或次數。
  * 如果是在 **CATCH** 區塊範圍之外呼叫這些函數，它們會傳回 **NULL**。 這些函數可以從 **CATCH** 區塊範圍內的任何位置擷取錯誤資訊。 例如，下列指令碼顯示包含錯誤處理函數的預存程序。 在 **TRY**…**CATCH**建構的 **CATCH**區塊中，會呼叫預存程序，並傳回錯誤的相關資訊。

**Catch Statement 示範**:

[sql]  
DECLARE @TestSQL VARCHAR(100) =&#8217;Try&#8217;

BEGIN TRY  
&#8212; Try to add String and number together  
SELECT @TestSQL+ 99

&#8212; if it passed the try statement, update the TestSQL variable  
SET @TestSQL = &#8216;Passed Try Statement&#8217;  
END TRY  
BEGIN CATCH  
SET @TestSQL = &#8216;Fall into Catch Statement&#8217;

&#8212; Show Error Information, when it fall into catch statement  
SELECT  
ERROR_NUMBER() AS ErrorNumber  
,ERROR_SEVERITY() AS ErrorSeverity  
,ERROR_STATE() AS ErrorState  
,ERROR_PROCEDURE() AS ErrorProcedure  
,ERROR_LINE() AS ErrorLine  
,ERROR_MESSAGE() AS ErrorMessage;

END CATCH

&#8212; Output  
SELECt @TestSQL  
[/sql]

**執行結果**:  
<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2937/14011490269_9274452587_z.jpg?resize=625%2C148" alt="TSQL Try and Catch -> Catch Result" width="625" height="148" data-recalc-dims="1" /> 

**Try Statement 示範**:

[sql]  
DECLARE @TestSQL VARCHAR(100) =&#8217;Try&#8217;

BEGIN TRY  
&#8212; Try to add String and number together  
SELECT @TestSQL+ 99

&#8212; if it passed the try statement, update the TestSQL variable  
SET @TestSQL = &#8216;Passed Try Statement&#8217;  
END TRY  
BEGIN CATCH  
SET @TestSQL = &#8216;Fall into Catch Statement&#8217;

&#8212; Show Error Information, when it fall into catch statement  
SELECT  
ERROR_NUMBER() AS ErrorNumber  
,ERROR_SEVERITY() AS ErrorSeverity  
,ERROR_STATE() AS ErrorState  
,ERROR_PROCEDURE() AS ErrorProcedure  
,ERROR_LINE() AS ErrorLine  
,ERROR_MESSAGE() AS ErrorMessage;

END CATCH

&#8212; Output  
SELECt @TestSQL  
[/sql]

**執行結果**:  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5151/14194879391_175bbc3c39_z.jpg?resize=203%2C149" alt="TSQL Try and Catch Statement Success" width="203" height="149" data-recalc-dims="1" /> 

**詳情可以參考以下網址**  
<a title="TSQL Try and Catch Block" href="http://technet.microsoft.com/zh-tw/library/ms175976.aspx" target="_blank">http://technet.microsoft.com/zh-tw/library/ms175976.aspx</a>

Hope you find it useful