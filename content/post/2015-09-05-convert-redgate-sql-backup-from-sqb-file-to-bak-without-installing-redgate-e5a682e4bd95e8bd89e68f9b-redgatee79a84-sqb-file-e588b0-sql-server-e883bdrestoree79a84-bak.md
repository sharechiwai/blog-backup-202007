---
id: 3493
title: 'Convert RedGate SQL Backup from sqb file to .bak without installing RedGate &#8211; 如何轉換 Redgate的 sqb file 到 SQL Server 能restore的 .bak 檔案'
date: 2015-09-05T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3493
permalink: '/2015/09/convert-redgate-sql-backup-from-sqb-file-to-bak-without-installing-redgate-%e5%a6%82%e4%bd%95%e8%bd%89%e6%8f%9b-redgate%e7%9a%84-sqb-file-%e5%88%b0-sql-server-%e8%83%bdrestore%e7%9a%84-bak/'
categories:
  - MSSQL Tips and Tricks
tags:
  - Database Maintenance
  - DBA
  - RedGate
---
最近公司更新的給客戶用使用的網頁..  
入面有一個**Bugs**.. 出現了很久&#8230;但是今天才發現..  
所以便要**restore** / **復原** 公司的 **Database backup** 去 **compare data** / **比較數據**  
由於公司的前**DBA** [現在以Contractor 的方式繼續在公司裡工作..] 不在英國的關係..要等待他回覆或 **Restore Database**..可能需要等幾天..  
最大的挑戰是.. 公司的**Database** 是用**RedGate** 的 **Database Backup tools** 來進行 **Backup** / **備份**的  
而同事們不不太清楚那個電腦安裝了**Redgate**的 **SQL Backup Pro**..  
還有.我們需要把 **redgate SQL backup tool backup format .sqb** 轉換成 **.bak** 來給**SQL Server**來 restore.

做了一會research 之後終於找到了解決方法..  
我們可以到以下載**SQL Backup convert tools**  
<a href="http://downloads.red-gate.com/labs/sqb2mtf.zip" target="_blank">http://downloads.red-gate.com/labs/sqb2mtf.zip</a>

解壓縮後我們可以執行以下指令去轉換 **SQL Backup**的格式  
E.G.  
首先..用**Command prompt** 去到儲存剛剛解壓縮的資料夾..  
之後執行以下指令 去使用<span style="color: #008000;"><strong>sqb2mtf.exe</strong></span>  
**sqb2mtf**的指令是這樣的  
**<span style="color: #008000;"><span style="color: #ff0000;">sqb2mtf</span> [input file e.g. .sqb 輪入那個 redgate的備份檔案 .sqb e.g.<span style="color: #ff0000;"> &#8220;f:\Database Backup\sharechiwai.sqb&#8221;</span>] [output file e.g. .bak 輪出的檔案名稱 .bak e.g. <span style="color: #ff0000;">&#8220;f:\Database Backup\sharechiwai.bak&#8221;</span>] [password / ]</span>**  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5617/20382458040_70c7c0a4d0_z.jpg?resize=625%2C144" alt="RedGate Database Backup tool command to convert .sqb to .bak via sqb2mtf tools" width="625" height="144" data-recalc-dims="1" />  
**E.G**

<pre>sqb2mtf "f:\Database Backup\sharechiwai.sqb" "f:\Database Backup\sharechiwai.bak"
</pre>

開始轉換了&#8230;這個程式會report完成轉換了多小..  
大家可以預計要等多久  
終於完成轉換了  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5753/20382449088_0689d25ca1_z.jpg?resize=625%2C211" alt="sqb2mtf process completed" width="625" height="211" data-recalc-dims="1" /> 

完成後 便會看到很多的 **_00.bak** \_01.bak.. \_13.bak 檔案  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5741/20383760959_fb789c5b1c_z.jpg?resize=625%2C433" alt="RedGate Database Backup conversion completed" width="625" height="433" data-recalc-dims="1" /> 

之後便可以使用 **Microsoft SQL Server** 來用這些檔案來 **Restore Database** 了

Hope you find it useful