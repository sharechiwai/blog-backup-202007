---
id: 3495
title: 'Convert RedGate SQL Backup from sqb file to .bak via GUI &#8211; 如何轉換 Redgate的 sqb file 到 SQL Server 能restore的 .bak 檔案 用 GUI 使用者介面'
date: 2015-09-08T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3495
permalink: '/2015/09/convert-redgate-sql-backup-from-sqb-file-to-bak-via-gui-%e5%a6%82%e4%bd%95%e8%bd%89%e6%8f%9b-redgate%e7%9a%84-sqb-file-%e5%88%b0-sql-server-%e8%83%bdrestore%e7%9a%84-bak-%e6%aa%94%e6%a1%88/'
categories:
  - Red-gate
tags:
  - Database Maintenance
  - DBA
  - MSSQL
  - TSQL Troubleshooting
---
在之前的網誌和大家介紹了如何使用 <span style="color: #008000;"><strong>sqb2mtf.exe</strong></span> 的指令來轉換 **RedGate SQL Backup Tool** 備份的 <span style="color: #008000;"><strong>SQL Database .sqb</strong></span> 檔案 轉換為一個 <span style="color: #008000;"><strong>Microsoft SQL Server</strong></span> 可以Restore/復原的 備份檔案格式 .bak

今天發現了..原來有一個有介面的功具.  
使用方法也十分簡單  
我們以到以下網址下載.. [不用安裝的]  
<a href="http://downloads.red-gate.com/labs/SQBConverterGUI.zip" target="_blank">http://downloads.red-gate.com/labs/SQBConverterGUI.zip</a>

解壓縮之後開啟 &#8220;<span style="color: #008000;"><strong>SQBConverterGUI.exe</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5646/20382457950_5123f0a6d6_z.jpg?resize=625%2C172" alt="SQBConverterGUI Tool to convert Redgate Database Backup file to .BAK" width="625" height="172" data-recalc-dims="1" /> 

之後**選擇要轉換到的格式**. E.G. **.BAK**  
**選擇檔案**  
如果有**密碼的輸入密碼**

<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5798/20383760859_e05101ddd7_z.jpg?resize=625%2C457" alt="SQBConverter GUI" width="625" height="457" data-recalc-dims="1" />  
之後按&#8221;**Convert** / **轉換**&#8221; 便可以  
這個程式亦都會報告狀況的  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5756/20382457870_7106193628_z.jpg?resize=625%2C578" alt="SQB Converter report progress" width="625" height="578" data-recalc-dims="1" /> 

等一會..如無意外便會完成

<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5685/20544215906_428f828638_z.jpg?resize=625%2C569" alt="SQB Converter Conversion completed" width="625" height="569" data-recalc-dims="1" />  
完成後 便會看到很多的 **_00.bak** **_01.bak**.. **_13.bak** 檔案  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5741/20383760959_fb789c5b1c_z.jpg?resize=625%2C433" alt="Lots of .bak files" width="625" height="433" data-recalc-dims="1" /> 

Hope you find it useful