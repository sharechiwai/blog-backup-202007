---
id: 2520
title: 'Using Loop in TSQL &#8211; 在TSQL中使用循環'
date: 2012-08-06T00:00:04+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2520
permalink: '/2012/08/using-loop-in-tsql-%e5%9c%a8tsql%e4%b8%ad%e4%bd%bf%e7%94%a8%e5%be%aa%e7%92%b0/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
因為之前公司出單是..有些客戶的資料錯過了2天..  
今天老闆問我們在出單前..檢查資料時有沒有一個程序把所有的客戶的數目資料都檢查一次..  
去確保他們每一天都有數據&#8230;ETC..  
因為這個步驟應該是我同事要做的..  
因為數據是經過他的Engine處理後才到我的程序上..  
所以如果數據真的有問題..即使我可以找到有潛在問題的數據時都太遲了..  
由於這個同事在放大假中..  
所以老闆要求我在下一個月前寫一個程序來避免有同樣問題出現..

想了一會&#8230;由於不想人手自己輸入 1- 31到Table上  
所以決定嘗試使用TSQL中的**While Loop**了  
原來**TSQL的While Loop和 VB/C#的While Loop是差不多的**

**解決方法**:

[sql]  
&#8212;- 首先Declare 一個Integer的變數  
&#8212;- 用來儲存While Loop當時的數值的  
DECLARE @i INT  
&#8212;- 之後Declare 到那一個數值時停止/結束While Loop  
DECLARE @LastNumber INT  
&#8212;- 初始化 變數  
SET @i = 1  
SET @LastNumber = 31  
&#8212;- While Loop的 Conditional Statement  
WHILE @i <= @LastNumber  
&#8212;- 開始  
BEGIN

&#8212;- SQL 語句&#8212;Action  
INSERT INTO ShareChiWai_WhileLoopDaySample  
( DayNo )  
VALUES ( @i )  
&#8212;- 把變數數值遞增  
SET @i = @i + 1  
&#8212;- 結束  
END  
[/sql]

**TSQL** 中的**While Loop**十分簡單

Hope you find it useful