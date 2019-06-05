---
id: 2300
title: 'Syntax error in MySQL Using LIKE in stored Procedure &#8211; 在MySQL的 Stored Procedure 上使用Like 出現語句錯誤'
date: 2011-12-02T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2300
permalink: '/2011/12/syntax-error-in-mysql-using-like-in-stored-procedure-%e5%9c%a8mysql%e7%9a%84-stored-procedure-%e4%b8%8a%e4%bd%bf%e7%94%a8like-%e5%87%ba%e7%8f%be%e8%aa%9e%e5%8f%a5%e9%8c%af%e8%aa%a4/'
categories:
  - MySQL Tips and Tricks
tags:
  - MSSQL
  - MSSQL VS MySQL
---
今天嘗試在**MySQL**上寫一個**Stored procedure** &#8230;  
上面會用到 &#8220;**LIKE**&#8220;這一個Operator  
這個**SQL** 是用來查詢 在**Table**上的 Description **field** 有沒有和 在Stored Procedure 上 傳送過來 以 這個**parameter** 開始或結尾的 記錄

[sql]  
SELECT *  
FROM localfood\_data\_tbl  
WHERE description LIKE &#8216;%&#8217;+ var_Description+ &#8216;%&#8217;;  
[/sql]

當我儲存這個Stored procedure 時.. 卻出現以下的錯誤  
&#8220;<span style="color: #ff0000;"><strong>SQL Error (1064): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near &#8216; + var_Description +&#8217;%&#8217;</strong></span>;&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b156cc56392d4ced8fe8b26be68d9468" alt="SQL Error (1064): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ' + var_Description +'%';" width="390" height="195" />  
我十分肯定這個語句在**MSSQL**上是沒有問題的

當我上網reseach 了一會之後發現..  
這是**MySQL**的 語句問題  
如果想把分開的文字串連在一起的話  
在**MSSQL**可以使用

[sql]  
SELECT &#8216;文字1&#8217; + &#8216;文字2&#8217;  
[/sql]

但是在**MySQL** 上卻需要使用**CONCAT** 這一個功能  
E.G.

[sql]  
SELECT CONCAT(&#8216;文字1&#8217;, &#8216;文字2&#8217;)  
[/sql]

最後我的SQL 變成了這樣子

[sql]  
SELECT *  
FROM localfood\_data\_tbl  
WHERE description LIKE CONCAT(&#8216;%&#8217;, var_Description,&#8217;%&#8217;)  
[/sql]

Hope you find it useful