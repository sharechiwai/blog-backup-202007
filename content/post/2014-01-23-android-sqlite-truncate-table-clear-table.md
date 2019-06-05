---
id: 3016
title: Android SQLite Truncate Table / Clear Table
date: 2014-01-23T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3016
permalink: /2014/01/android-sqlite-truncate-table-clear-table/
categories:
  - .Net Tips And Tricks
tags:
  - Android
  - Java
  - SQLIte
---
又開始學習寫**Android Apps**  
已經忘記了怎樣用**Android** 和怎樣寫**Java Program** 了

今天嘗試在**Android SQLite** 時  
想寫一個功能來**Truncate** 這個**Database**  
E.G.

[java]  
db.execSQL("TRUNCATE TABLE " + TABLE_SHARECHIWAI);  
[/java]

誰不知..當我執行這個功能是出現以下錯誤信息..  
<span style="color: #ff0000;"><strong>&#8220;(1) near &#8220;TRUNCATE&#8221;: syntax error&#8221;</strong></span>  
<img class="alignnone" alt="(1) near " src="https://i2.wp.com/farm8.staticflickr.com/7348/12488081745_99d5cbd1fa_d.jpg?resize=412%2C63" width="412" height="63" data-recalc-dims="1" />  
原來**SQLite** 不支援**Truncate Table**的  
所以如果大家想清理**SQLite Table** 上的資料的話便要使用  
**DELETE FROM**  
或是  
**DROP TABLE** 之後再建立多一次 這個Table

[java]  
db.execSQL("DELETE FROM " + TABLE_SHARECHIWAI);  
[/java]

Hope you find it useful