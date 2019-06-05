---
id: 801
title: 'VB.Net mysql.data.dll Connector/Net Exception Unable to convert MySQL date/time value to   System.DateTime'
date: 2010-10-12T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=801
permalink: /2010/10/vb-net-mysql-data-dll-connectornet-exception-unable-to-convert-mysql-datetime-value-to-system-datetime/
categories:
  - .Net Tips And Tricks
  - MySQL Tips and Tricks
---
今日有朋友在VB.Net 上使用 MySQL 的 **ADO.NET driver for MySQL** [mysql.data.dll ]..時候 出現了以下的錯誤句子  
<span style="color: #ff0000;"><strong>&#8220;Unable to convert MySQL date/time value to System.DateTime&#8221;</strong></span>  
做了一會資料搜集之後..終於找到了解決方法了

只要在**Connection String** 上加入以下設定便可  
<span style="color: #339966;"><strong>Allow Zero Datetime=True</strong></span>

更改了的**Connection String** 是這樣子的  
**<span style="color: #339966;">Dim cs as String = &#8220;Database=TestDataBaseName; Data Source=localhost;User Id=root;Password=password; Allow Zero Datetime=True;&#8221;</span>**

Hope you find it useful