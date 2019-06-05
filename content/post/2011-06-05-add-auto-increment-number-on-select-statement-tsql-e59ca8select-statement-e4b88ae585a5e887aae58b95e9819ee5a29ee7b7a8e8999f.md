---
id: 1791
title: 'Add Auto-Increment Number on Select Statement (TSQL )  &#8211; 在SELECT Statement 上入自動遞增編號'
date: 2011-06-05T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1791
permalink: '/2011/06/add-auto-increment-number-on-select-statement-tsql-%e5%9c%a8select-statement-%e4%b8%8a%e5%85%a5%e8%87%aa%e5%8b%95%e9%81%9e%e5%a2%9e%e7%b7%a8%e8%99%9f/'
categories:
  - MSSQL Tips and Tricks
---
今日繼續改善自己所寫的program  
程式上有一個功能是用來打印報告的  
主要是跟據 由於客戶很多的關係..  
我們要打這些報告排序..  
沒有那麼多報告的客戶會先Print..  
但是又要打他們分Printer Group 來Print..  
這是因為公司有6部Printer的關係..  
所以我們要好好運用他們..  
令到等待列印的時間縮短&#8230;

我之前寫的程式/**SQL Insert Statement**只可以做到把  
總結了的資料加進Table 上..[因為我們要使用這個Table來分配Print Group]  
之後人手在**SQL Server Management Studio**或在我寫的程式上排序

在天在自己Review 自己寫了一年多的Code 的時候..  
終於想到了解決方法了  
就要只要我能夠在 找到Summary 的資料時候..  
可以在資料上加入一個 **Auto-increment number/自動遞增編號**  
問題是&#8230;如何可以在 **SELECT Statement上加入Row ID** 呢?

公司有同是介紹我寫一個有**Auto-Increment Number 的Temp Table**  
E.G.

[sql]  
DECLARE @Temp AS TABLE(RowId INT IDENTITY(1,1), Username VARCHAR(50), City VARCHAR(100), Country VARCHAR(100) )

[/sql]

之後把Summary 的資料Insert 進去..便可以有Row ID了..  
最後當然是做一個SELECT Statement 和DROP這個Temp table..

&nbsp;

這了數分鐘.突然間想到..當初想使用**SQL2008/SQL2005**  
是因為我們想使用**SQL2005** 之後推出的**ROW_NUMBER** 功能..

之後我便找到了**解決方法**了

如果我們想在**SELECT Statement 上加入ROW ID** 我們可以 使用

[sql]  
ROW_NUMBER() OVER ( ORDER BY {FieldName you want to order by})  
[/sql]

E.G.

[sql]  
SELECT Username, City, Country, ROW\_NUMBER() OVER ( ORDER BY Country) AS ROW\_ID  
FROM ShareChiWai_Table  
[/sql]

便可以在**SELECT Statement 上加入Auto Number** 了

有關**Row_Number()**的使用方法可以看看以下URL  
 <a title="TSQL Row_Number() 使用方法" href="http://msdn.microsoft.com/en-us/library/ms186734.aspx" target="_blank">http://msdn.microsoft.com/en-us/library/ms186734.aspx</a>  
Hope you find it useful