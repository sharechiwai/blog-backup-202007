---
id: 809
title: 'Cannot resolve the collation conflict between &#8220;SQL_Latin1_General_CP1_CI_AS&#8221; and   &#8220;Latin1_General_CI_AS&#8221; in the UNION operation.'
date: 2010-10-10T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=809
permalink: /2010/10/cannot-resolve-the-collation-conflict-between-sql_latin1_general_cp1_ci_as-and-latin1_general_ci_as-in-the-union-operation/
categories:
  - MSSQL Tips and Tricks
---
今日有朋友在寫一條TSQL 的 語句時 出現了這個 **Error Message**  
**<span style="color: #ff0000;">Cannot resolve the collation conflict between &#8220;SQL_Latin1_General_CP1_CI_AS&#8221; and &#8220;Latin1_General_CI_AS&#8221; in the UNION operation.</span>**

每當遇到 <span style="color: #ff0000;"><strong>Cannot resolve the collation conflict </strong></span> 這個問題時  
通常是因為把兩個不同編碼/排序規則 的 資料表連結在一起時出現的  
以上的Error Message 說有一個Table 的Collation 是&#8221;SQL\_Latin1\_General\_CP1\_CI_AS&#8221;  
而另一個是 &#8220;Latin1\_General\_CI_AS&#8221;

解決方法很簡單  
可以在有 文字的Fields 上加上 **COLLATE DATABASE_DEFAULT**  
這便會把 **Collation**轉成 資料庫默認的 模式了  
和數字有關的Field 是不用加這個 Key words 的  
E.G. 以**AdventureWorks Database** 的 Table 做例子

我先把 AdventureWorks Database 複製到另一個資料庫  
之後嘗試打2個資料庫的資料連在一起

<span style="color: #008000;">SELECT Title, FirstName, MiddleName, EmailAddress, EmailPromotion, ModifiedDate<br /> FROM  AdventureWorks.Person.Contact<br /> WHERE ContactID<10<br /> UNION<br /> SELECT Title, FirstName, MiddleName, EmailAddress, EmailPromotion, ModifiedDate<br /> FROM  ShareChiWai.Person.Contact<br /> WHERE ContactID>10</span>

當你遇到  
<span style="color: #ff0000;"><strong>Cannot resolve the collation conflict between &#8220;SQL_Latin1_General_CP1_CI_AS&#8221; and &#8220;Latin1_General_CI_AS&#8221; in the UNION operation.</strong></span> 時  
你可以用以下方法解決

<span style="color: #008000;">SELECT Title, FirstName, MiddleName, EmailAddress, EmailPromotion, ModifiedDate<br /> FROM  AdventureWorks.Person.Contact<br /> WHERE ContactID<10<br /> UNION<br /> SELECT Title <strong>COLLATE DATABASE_DEFAULT</strong>,<br /> FirstName <strong>COLLATE DATABASE_DEFAULT</strong>,  MiddleName <strong>COLLATE DATABASE_DEFAULT,</strong> EmailAddress <strong>COLLATE DATABASE_DEFAULT</strong>,<br /> EmailPromotion, ModifiedDate &#8212;<span style="color: #0000ff;">由於 EmailPromotion 和 ModifiedDate 不是文字..所以不用加 COLLATE DATABASE_DEFAULT</span><br /> FROM  ShareChiWai.Person.Contact<br /> WHERE ContactID>10</span>

有時候這可能在 **Join** 上面出現的  
這便要在 **Join** 的 地方加了  
E.G.

SELECT t.*  
FROM Table1  
INNER JOIN Table2  
ON Table1.Field1 = Table2.Field1 COLLATE DATABASE_DEFAULT

Hope you find it Useful