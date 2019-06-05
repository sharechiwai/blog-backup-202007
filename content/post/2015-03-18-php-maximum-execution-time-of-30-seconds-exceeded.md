---
id: 3406
title: PHP Maximum execution time of 30 seconds exceeded
date: 2015-03-18T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3406
permalink: /2015/03/php-maximum-execution-time-of-30-seconds-exceeded/
categories:
  - PHP 新手筆記
tags:
  - PHP Troubleshooting
---
今天寫了一個**PHP** 功能去負責把一些資料從**JSON** 加到 **MySQL Database**上  
可能是資料比較多的關係..  
所以他便出現了這樣的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Message: Maximum execution time of 30 seconds exceeded</strong></span>&#8221;  
&#8220;<span style="color: #ff0000;"><strong>Filename: mysql/mysql_driver.php</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8711/16364505664_16ed54c1f2_z.jpg?resize=625%2C240" alt="Maximum execution time of 30 seconds exceeded" width="625" height="240" data-recalc-dims="1" />  
開頭還以為是**MySQL Database**的 **Timeout 問題**  
做了一會Research 終於找到解決方法了

**解決方法**  
我們只需要在執行的PHP 頁面上overwrite 了原先PHP 定下的 Execution time limit 便可以  
大家可以在頁面上加上 以下功能便可以了 <span style="color: #008000;"><strong>set_time_limit(&#8220;數值 以秒&#8221;)</strong></span> 來作單位  
**E.G.**

<pre>// Set Timeout for 3 minutes 把Timeout設定為三分鐘 [180秒]
set_time_limit(180);
</pre>

之後再執行之前的功能便沒有出現**Timeout**了

Hope you find it useful