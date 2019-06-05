---
id: 3256
title: 'PHP Time with microseconds &#8211; 如何在PHP 上取後  日期時間包括微秒'
date: 2014-06-30T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3256
permalink: '/2014/06/php-time-with-microseconds-%e5%a6%82%e4%bd%95%e5%9c%a8php-%e4%b8%8a%e5%8f%96%e5%be%8c-%e6%97%a5%e6%9c%9f%e6%99%82%e9%96%93%e5%8c%85%e6%8b%ac%e5%be%ae%e7%a7%92/'
categories:
  - PHP 新手筆記
tags:
  - TimeStamp
---
今天嘗試在**PHP** 做測試時想使用日期時間包括**微秒**/**microsecond**來做一些記錄  
但是當我使用 &#8220;**u**&#8221; 這個**format** / **格式**時..不論什麼時候..他只會出現 &#8220;**000000**&#8221; 的結果

做了一會學research後發現..  
**Date()**這個功能只會輸出&#8221;**000000**&#8220;為**Microsecords**

所以我們便要自行定義一個小小的功能來解決這個問題

**解決方法**:

為了方便自己..所以我建立了一個新的function  
這個功能可以自己定義日期時間輸出的格式

<pre>function CurrentDateTimeWithMicroseconds($format = "Y-m-d H:i:s") {
    // 設定microtime 為 true 令他可以輸出 Unix timestamp with microseconds
    $timestamp = microtime(true);
    
    // 取出microseconds
    $microseconds = (int) round(($timestamp - floor($timestamp)) * 1000.0, 0);
    
    // 把結果組合一起..
    return date($format . $microseconds, $timestamp);
}
</pre>

**使用方法**:

<pre>echo CurrentDateTimeWithMicroseconds();
</pre>

<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3920/14629995630_5586f6c830_z.jpg?resize=504%2C84" alt="PHP Date Time with Microseconds" width="504" height="84" data-recalc-dims="1" /> 

<a title="PHP DateTime with micro seconds Demo" href="http://sharechiwai.com/phpdemo/demo_hubs/php_datetime_with_microseconds" target="_blank">PHP Time with microseconds Demo</a>

Hope you find it useful