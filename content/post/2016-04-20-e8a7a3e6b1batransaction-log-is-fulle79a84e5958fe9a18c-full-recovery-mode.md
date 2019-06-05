---
id: 3631
title: '解決Transaction Log is Full的問題 &#8211; Full Recovery Mode'
date: 2016-04-20T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3631
permalink: '/2016/04/%e8%a7%a3%e6%b1%batransaction-log-is-full%e7%9a%84%e5%95%8f%e9%a1%8c-full-recovery-mode/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - Database Management
  - Transaction Log
---
之前介紹過  &#8211; [如何解決Transaction Log is Full的問題 &#8211; Simple Recovery Mode](http://blog.sharechiwai.com/2016/04/解決transaction-log-is-full的問題-simple-recovery-mode)

今天想和大家介紹怎樣**解決Transaction Log is Full的問題 &#8211; Full Recovery Mode**  
原來**Database** 的**Recovery Mode** 設定為 &#8220;Full&#8221;的時候

即使做了**Database Full Backup** 也不能解決**Transaction Log is Full的問題**

其實**解決方法**十分簡單 和之前的網誌的解決方法差不多

唯一改變的是 &#8220;**Backup type**:&#8221; 選擇 &#8220;**Transaction Log**&#8221;

**E.G.**  
在**SQL Server Management Studio** 的**Database** 上Right Click  
之後選擇&#8221;**Task**&#8220;->&#8221;**Backup**&#8221;  
<img class="alignnone" style="height: auto; max-width: 100%; border: 0px; border-radius: 3px; box-shadow: rgba(0, 0, 0, 0.2) 0px 1px 4px; color: #444444; font-family: 'Open Sans', Helvetica, Arial, sans-serif; font-size: 14px; font-style: normal; font-variant: normal; font-weight: normal; letter-spacing: normal; line-height: 24px; orphans: auto; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; widows: 1; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: #ffffff;" src="https://i2.wp.com/farm2.static.flickr.com/1713/25837943993_7e4e9f202e_z.jpg?resize=625%2C517" alt="SSMS -> Backup Database" width="625" height="517" data-recalc-dims="1" /> 

在&#8221;**Back Up Database 對話方塊**&#8221; 上 的 &#8220;**Backup type**:&#8221; 選擇 &#8220;**Transaction Log**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1591/26374586861_8e5eabc39d_z.jpg?resize=625%2C458" alt="Backup Transaction Log - SSMS" width="625" height="458" data-recalc-dims="1" />  
之後選擇**Backup** 到的地點..按**OK** 便可以了

Hope you find it useful