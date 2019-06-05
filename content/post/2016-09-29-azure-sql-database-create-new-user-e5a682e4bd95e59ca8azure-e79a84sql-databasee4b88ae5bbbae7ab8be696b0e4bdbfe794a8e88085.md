---
id: 3756
title: Azure SQL Database Create New User -如何在Azure 的SQL Database上建立新使用者
date: 2016-09-29T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3756
permalink: '/2016/09/azure-sql-database-create-new-user-%e5%a6%82%e4%bd%95%e5%9c%a8azure-%e7%9a%84sql-database%e4%b8%8a%e5%bb%ba%e7%ab%8b%e6%96%b0%e4%bd%bf%e7%94%a8%e8%80%85/'
categories:
  - Microsoft Azure
tags:
  - Azure
  - Azure SQL Service
---
最近終於開始使用Azure的SQL Database了  
之前因為感到太貴的關係。。所以沒有使用　Azure的Database Service

建立完Database之後  
當然要建立新使用者&#8230; 去增加安全性  
當我還以為可以像之前的Local的Database那樣有個UI來幫忙建立使用者..  
誰不知當我按下建立**New User** 時..

他出現了一些**Script的Template**..  
[<img class="alignnone size-medium wp-image-3757" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?resize=300%2C105" alt="Add New User Script from Azure AQL Service" width="300" height="105" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?resize=300%2C105 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?resize=768%2C268 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?resize=1024%2C357 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?resize=624%2C218 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?w=1488 1488w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png?w=1250 1250w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/09/CreateNewUserScript.png)  
好像有點複雜  
所以使想建立這一篇筆記..  
方便大家在Azure上建新的database 使用者

**解決方法**  
首先我們要似**Azure SQL Server**的 **Admin**登入  
之前選擇 &#8220;**master**&#8221; database  
再執行 **Create Login** 這個**Command**

<pre>-- Create login to database server
USE [master]
CREATE LOGIN SampleDBUser WITH PASSWORD = 'very secure password';

</pre>

完成後..便會在這個**Azure SQL Server**上建立一個可以登的使用者  
之後我們便可以**Assign** 這個使用都可以access那些**Database**和有什麼**權限**了

首先我們先在**Management Studio**上選擇想給與這個新使用者權限的database  
使用use [database name] 也是可以的  
之後便可以用script來Add user 和 assign role 了

<pre>-- Create user on database
USE [sampledatabase]
CREATE USER SampleDBUser FOR LOGIN [SampleDBUser]; 

-- Assign roles
ALTER ROLE db_owner ADD MEMBER LocalIssuesDBUser; 
</pre>

Hope you find it useful