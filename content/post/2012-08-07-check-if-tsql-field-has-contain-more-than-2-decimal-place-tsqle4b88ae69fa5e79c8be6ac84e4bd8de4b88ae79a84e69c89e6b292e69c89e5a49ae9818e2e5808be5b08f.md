---
id: 2522
title: 'Check if TSQL field has contain more than 2 decimal place &#8212; TSQL上查看欄位上的有沒有多過2個小數位的資料'
date: 2012-08-07T00:00:27+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2522
permalink: '/2012/08/check-if-tsql-field-has-contain-more-than-2-decimal-place-tsql%e4%b8%8a%e6%9f%a5%e7%9c%8b%e6%ac%84%e4%bd%8d%e4%b8%8a%e7%9a%84%e6%9c%89%e6%b2%92%e6%9c%89%e5%a4%9a%e9%81%8e2%e5%80%8b%e5%b0%8f/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
每個月同事都要把我寫的Invoice Program的數據輸出到一些會計軟件的格式..  
方便其他公司的會計部入資料..  
很可惜&#8230;由於公司的數據的**Data Type**是**Money**  
但是從會計的角度來看&#8230;  
**最小的數值是1 penny** E.G. **0.01英鎊**&#8230;  
是不可以有0.001英鎊的&#8230;因為英鎊最小面額的數值是1 Penny E.G 0.01英鎊..  
不知道為什麼..可能是要處理的數據是4個小數位的關係..  
久不久便會有些資料&#8230;處理完成後會有多過2個弓數位的數值1..  
令到不能Export到會計軟件上&#8230;  
所以便要人手的找出有問題的數據..**看看那一個record有多過2個小數位**

這個問題出現了很久..  
今天終止有時間去思考一下更好的解決方法  
方便找出有問題的資料&#8230; E.G. 多過2個小數位的record

之後便想到一個Quick Fix的解決方法

就是我們可以寫一個簡單的**TSQL** 用 **WHERE Round(Fieldname,2) <>Fieldname**  
**來找出多過2個小數位的record**  
**E.G.**  
 **如果資料是2個小數位的話..Round(FieldName,2) 的數值會和 FieldName的一樣的**  
 **如果資料是2個小數位的話&#8230;Round(FieldName,2) 便會小過或大過FieldName的數值**了&#8230;  
**E.G**.

[sql]  
SELECT *  
FROM ShareChiWai_SampleData  
WHERE ROUND(FieldName,2) <> FieldName  
[/sql]

**e.g. **  
 **Round(0.001,2) = 0**  
 **Round(0.01,2) = 0.01**

Hope you find it useful