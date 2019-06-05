---
id: 2839
title: Get SQL Server information from connection string via Web.Config / App.Config
date: 2013-05-06T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2839
permalink: /2013/05/get-sql-server-information-from-connection-string-via-web-config-app-config/
categories:
  - .Net Tips And Tricks
tags:
  - Connection String
---
公司的新Project 終於要**Deploy**到Server上給同事測試了&#8230;  
由於還沒有想到怎樣可以很方便的**Dynamic**地把**SSRS** 的Database Connection  
由**Live** 轉為 **Dev**  
所以我們便Replicate 了要用的Report 一個連接到Live的Server上的數據..  
另一個連接到Dev 上..

**Live**和**Dev**的數據是以**Connection String**來 選擇的  
由於不知道怎樣可以**Pass Connection string 到SSRS** 的關係..  
所以便要想想辦法..看看如何 找出 **Web.Config** / **App.Config**上的 **Connection string** 屬性  
如**Server**名, 便用者名稱.. **Database**名等等 來決正

我的例子是Database和 Username **Live** 和 **Dev Server**都是一樣的..  
不同之處只是在Server名上

如何可以在**Connection String** 上找出 **Connection String** 上的 Server 名呢..

**解決方法**  
我們可以使用**SqlConnectionStringBuilder** 來分析我們的**Connection Strin**g 以便找出 我們的**Connection String** 資訊  
E.G.

[xml]  
<add name="ApplicationServices" connectionString="Data Source=ShareChiWaiServer;Initial Catalog=ShareChiWaiSample;User Id=iBillUser;Password=iBill2011;" providerName="System.Data.SqlClient" />  
[/xml]  
[csharp]  
//建立 SqlConnectionStringBuilder Object  
SqlConnectionStringBuilder sqlConStrBuilder =  
new SqlConnectionStringBuilder(ConfigurationManager.ConnectionStrings["ApplicationServices"].ConnectionString);

//取得 Database 名  
Console.WriteLine("Database Name: " + sqlConStrBuilder.InitialCatalog);  
//取得 Server 名  
Console.WriteLine("Server Name: " + sqlConStrBuilder.DataSource);  
//取得 Username  
Console.WriteLine("UserID: " + sqlConStrBuilder.UserID);  
[/csharp]

Hope you find it useful