---
id: 1832
title: 'TSQL How to check if temporary table already exist &#8211; 在TSQL 上如何檢查出暫存的表已經存在?'
date: 2011-06-30T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1832
permalink: '/2011/06/tsql-how-to-check-if-temporary-table-already-exist-%e5%9c%a8tsql-%e4%b8%8a%e5%a6%82%e4%bd%95%e6%aa%a2%e6%9f%a5%e5%87%ba%e6%9a%ab%e5%ad%98%e7%9a%84%e8%a1%a8%e5%b7%b2%e7%b6%93%e5%ad%98%e5%9c%a8/'
categories:
  - MSSQL Tips and Tricks
tags:
  - SQL
---
最近有朋友問怎樣才可以知道 **SQL 中的Temporary Table/暫存表** 已經存在?  
因為很多時候我們都有使用到**Temporary Table/暫存表**.. 方便自己寫**SQL Query**和 檢查結果

有時候我們也會在**Stored procedure**上 使用**Temporary Table**..  
但是有時候可能是因為資料的錯誤..  
令到**Stored Procedure** 在執行到一半的時候便停止了  
這時候之前建立的**Temporary Table**. 可能仍然還存在**Database**上..  
所以當再次執行這個**Stored Procedure** 時..  
因為會建立**Temp Table**的關係..所以有可能會會出現以下的錯誤  
&#8220;<span style="color: #ff0000;"><strong>Msg 2714, Level 16, State 6, Line 1</strong></span>  
<span style="color: #ff0000;"><strong> There is already an object named &#8216;#test&#8217; in the database.</strong></span>&#8221;  
[<img class="alignnone" title="Temp Table Already Exist" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4dbd4d95f90648edae6300336dd2f70c/renditions/fullsize.jpg?resize=462%2C110" alt="" width="462" height="110" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4dbd4d95f90648edae6300336dd2f70c/renditions/fullsize.jpg)

解決方法  
我們可以用一些**SQL** 程式碼來檢查**Temp Table** 是否存在..  
之後再決定做什麼  
我們可以用**<span style="color: #339966;">OBJECT_ID() </span>**這個方法來找出**Object** 是否存在  
E.G.

[sql]  
OBJECT_ID(&#8216;tempdb..TempTableName&#8217;)  
[/sql]

以下是小小的例子

&nbsp;

[sql]  
DECLARE @TempTableName VARCHAR(100) = &#8216;#Test&#8217;

IF OBJECT_ID(&#8216;tempdb..&#8217;+@TempTableName) is not NULL  
SELECT &#8216;Temp Table Exist&#8217; AS Result  
ELSE  
SELECT &#8216;Temp Table Does not Exist&#8217; AS Result  
&#8211;Expected result &#8216;Temp Table Does not Exist&#8217;

CREATE TABLE #test(  
CustomerCode VARCHAR(10)  
)  
IF OBJECT_ID(&#8216;tempdb..&#8217;+@TempTableName) is not NULL  
SELECT &#8216;Temp Table Exist&#8217; AS Result  
ELSE  
SELECT &#8216;Temp Table Does not Exist&#8217; AS Result  
DROP TABLE #Test  
&#8211;Expected result &#8216;Temp Table Exist&#8217;

IF OBJECT_ID(&#8216;tempdb..&#8217;+@TempTableName) is not NULL  
SELECT &#8216;Temp Table Exist&#8217; AS Result  
ELSE  
SELECT &#8216;Temp Table Does not Exist&#8217; AS Result  
&#8211;Expected result &#8216;Temp Table Does not Exist&#8217;  
[/sql]

執行以上**SQL** 之後的結果

[<img class="alignnone" title="MSSQL Check If Temp Table Exist Result" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8e5afe70324a42c0b60819a94d0dd3f0/renditions/fullsize.jpg?resize=224%2C268" alt="" width="224" height="268" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8e5afe70324a42c0b60819a94d0dd3f0/renditions/fullsize.jpg)

Hope you find it useful