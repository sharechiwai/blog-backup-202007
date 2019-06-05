---
id: 2855
title: 'TSQL &#8211; How to Get the Transaction Log Size -MSSQL'
date: 2013-05-09T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2855
permalink: /2013/05/tsql-how-to-get-the-transaction-log-size-mssql/
categories:
  - MSSQL Tips and Tricks
tags:
  - Transaction Log
---
今天同事說他的程式出現了一個**Database Error**..  
之後我便去看看是什麼問題&#8230;  
原來是Database 的 **Transaction Log Full**..

由於他是正在做一些很大**Transaction**的 SQL Query 入面有很多Update Data 的Query  
而這個Database 的**Transaction Log**又很滿..  
所以便出現了這個問題了

由於我不是公司的**DBA**..而 **DBA** 又沒有交代 當**Transaction Log**滿時應該怎麼辨..  
我知道最簡單的方法是 **Truncate** 這個**Transaction Log**  
之後那位同事便可以繼續他的**Query**.

但是聽說..我們不應該**Truncate Transaction Log**的..  
這便令到資料庫不能**Restore via transaction log.**. [這個還是要多多做Research才能了解]

最後我只做了Research去給同事們一個Alert..  
就是使用**Query** 去檢查**Transaction Log**的大小..

大家可以使用以下的**Query**去檢討**Transaction Log**的大小

[sql]  
DBCC SQLPERF ( LOGSPACE )  
[/sql]

[<img class="alignnone size-full wp-image-2856" alt="DBCC SQLPERF ( LOGSPACE )" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SQLPERF.png?resize=625%2C333" width="625" height="333" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SQLPERF.png)

Hope you find it useful