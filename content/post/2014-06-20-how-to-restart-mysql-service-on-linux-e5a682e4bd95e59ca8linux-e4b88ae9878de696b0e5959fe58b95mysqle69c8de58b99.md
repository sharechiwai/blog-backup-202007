---
id: 3244
title: 'How to restart MySQL Service on Linux &#8211; 如何在Linux 上重新啟動MySql服務?'
date: 2014-06-20T00:00:34+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3244
permalink: '/2014/06/how-to-restart-mysql-service-on-linux-%e5%a6%82%e4%bd%95%e5%9c%a8linux-%e4%b8%8a%e9%87%8d%e6%96%b0%e5%95%9f%e5%8b%95mysql%e6%9c%8d%e5%8b%99/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - mysql
  - Ubuntu
---
今天我的網誌不知道為什麼有**Database Error**

<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2901/14760542516_2e4861081c_z.jpg?resize=625%2C279" alt="WordPress - Error Establishing a database connection" width="625" height="279" data-recalc-dims="1" /> 

為了最快可以令網誌可以繼續運作..  
所以我決定嘗試重新啟動在**Ubuntu** 上的 **MySQL Service**看看能不能解決這個問題&#8230;

如何在**Linux** 上重新啟動**MySql**服務呢?

**解決方法**十分簡單..  
我們可以用**Sudo** 執行以下的指令便可以了

**重新啟動MySql服務**

<pre>sudo /etc/init.d/mysql restart
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3841/14780392361_c70e89bf5d_z.jpg?resize=625%2C112" alt="Linux Restart MySQL Services" width="625" height="112" data-recalc-dims="1" /> 

**暫停MySql服務**

<pre>sudo /etc/init.d/mysql stop
</pre>

**啟動MySql服務**

<pre>sudo /etc/init.d/mysql start
</pre>

Hope you find it useful