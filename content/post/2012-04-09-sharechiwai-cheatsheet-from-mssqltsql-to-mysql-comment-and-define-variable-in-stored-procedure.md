---
id: 2319
title: 'ShareChiWai CheatSheet  &#8211; From MSSQL/TSQL to MYSQL &#8211; Comment and Define Variable in Stored Procedure'
date: 2012-04-09T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2319
permalink: /2012/04/sharechiwai-cheatsheet-from-mssqltsql-to-mysql-comment-and-define-variable-in-stored-procedure/
categories:
  - MySQL Tips and Tricks
tags:
  - ShareChiWai Cheatsheet
  - TSQL VS MySQL
---
最近參與了很多的**Hack Event** 很多時候都是使用**MySQL**做**BackEnd**&#8230;  
因為很小Teammate有一個**MSSQL Server** 的空間可以給我們便用..  
所以便常常用到**MySQL**了  
由於是**Hack Event**的關係&#8230;所以我們只有很小時間去完成想做的功能..  
為了方便自己不用花時間搜尋一些自己之前解決過的問題  
所以便決定寫低這些不太起眼..  
但是有時候需要用時又可能突然間想不到的程式碼..  
今天和大家分享的是 **MSSQL** 和 **MySQL** 有一些**Syntax**的不同..方便自己Look Up.  
**第一個分別是 Comment**  
今天想在**MySQL**的**Stored Procedure** 上Comment out一些Code來做測試..  
當我使用**TSQL的Comment** 語句後嘗試儲存時便出現錯誤信息了  
在**TSQL**/**MSSQL**我們可以便用&#8221;**&#8212;**&#8221; 來**Comment**的們的**SQL** Code  
E.g.

**T-SQL**

[sql]  
&#8211;This stored proccedure is used to&#8230;  
[/sql]

在**MySQL**我們需要使用 &#8220;**##**&#8221; 來**Comment**我們的SQLCode  
E.G.  
**MySQL**

[sql]  
\## 在MySQL上這是用來Comment Out程式碼的  
[/sql]

**第二個問題是怎樣在Stored proceure內定義一些變數用來暫時儲存資料之用**

在**T-SQL**上我們可以使用**DECLARE** 之後用**SELECT** 或**SET** 來**Assige 內容到這些變數上**  
E.G.  
**T-SQL**

[sql]  
&#8211;Define Variable in T-SQL  
DECLARE @TestingVariable AS VARCHAR(20) =&#8217;Hello&#8217;  
&#8211;我們還可以用以下方法來Assign Variable的  
&#8211;使用Select  
SELECT @TestingVariable = &#8216;How Are You&#8217;  
SELECT @TestingVariable  
&#8212; 使用SET  
SET @TestingVariable = &#8216;你好嗎?&#8217;  
SELECT @TestingVariable  
&#8211;或使用SQL Select statement  
SELECT @TestingVariable = Field1  
FROM Table1

&#8211;這個句子要確定他只return 一行的結果, 如果不是的話 他會把最後的record加進這個變數上  
[/sql]

**MySQL**

[sql]  
##Define Variable in MySQL  
SET @TestingVariable =&#8217;Hello&#8217;;

##或使用SQL Select statement  
SELECT Field1 INTO @TestingVariable  
FROM Table1  
##這個句子要確定他只return 一行的結果 , 如果不是的話 他只會出現錯誤  
[/sql]

如果在**T-SQL上**希望在SQL句子上**Assign 多過一個Variable**我們可以

[sql]  
DECLARE @MaxScore Int=0  
DECLARE @MinScore Int=0  
DECLARE @AverageScore float=0

&#8211;Assign more than 1 variable in SQL Statement  
SELECT @MaxScore = MAX(Score), @MinScore = MIN(Score), @Average = AVG(Score)  
FROM ExamResult  
[/sql]

在**MySQL**我們可以

[sql]  
SET @MaxScore =0  
SET @MinScore =0  
SET @AverageScore =0

##Assign more than 1 variable in SQL Statement  
SELECT @MaxScore = MAX(Score), @MinScore = MIN(Score), @Average = AVG(Score)  
FROM ExamResult  
[/sql]

今天的**TSQL VS MySQL**到為止..  
將來有時間會Upload 更多有關**TSQL VS MySQL**的網誌敬請留意  
Hope you find it useful