---
id: 3629
title: '解決Transaction Log is Full的問題 &#8211; Simple Recovery Mode'
date: 2016-04-18T00:00:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3629
permalink: '/2016/04/%e8%a7%a3%e6%b1%batransaction-log-is-full%e7%9a%84%e5%95%8f%e9%a1%8c-simple-recovery-mode/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - Transaction Log
---
經過一會兒學習之後..終於學會了怎樣好好地解決<span style="color: #ff0000;"><strong>Transaction Log Is Full</strong></span>的問題

之前和大家介紹過  
怎樣取得**Transaction Log**的大小資訊  
E.G. **Transaction Log**的檔案大小和用了多小真實空間

### <a href="http://blog.sharechiwai.com/2013/05/tsql-how-to-get-the-transaction-log-size-mssql/" rel="bookmark">TSQL – How to Get the Transaction Log Size -MSSQL</a> {.entry-title}

今天想和大家介紹怎樣解決  
如果你的**Database** 是 **Simple Mode**的話

你們只需要把**Database** 做一個**Full Backup**便可以解決這個問題了

在**SQL Server Management Studio** 的**Database** 上Right Click  
之後選擇&#8221;**Task**&#8220;->&#8221;**Backup**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1713/25837943993_7e4e9f202e_z.jpg?resize=625%2C517" alt="SSMS -> Backup Database" width="625" height="517" data-recalc-dims="1" /> 

在&#8221;**Back Up Database 對話方塊**&#8221; 上 的 &#8220;**Backup type:**&#8221; 選擇 &#8220;**Full**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1638/25835926924_3385aeba9d_z.jpg?resize=625%2C458" alt="Backup Database Dialogue Box" width="625" height="458" data-recalc-dims="1" />  
之後選擇**Backup** 到的地點..按**OK** 便可以了

Hope you find it useful