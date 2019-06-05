---
id: 3540
title: 'PHP Error: Maximum execution time of 60 seconds exceeded'
date: 2016-01-08T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3540
permalink: /2016/01/php-error-maximum-execution-time-of-60-seconds-exceeded/
categories:
  - PHP 新手筆記
tags:
  - PHP
  - PHP Troubleshooting
---
今日當試在執行一個自己寫的**PHP function** 來 **Import data**的時候 出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Error: Maximum execution time of 60 seconds exceeded</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1720/23976063384_e00418e7a4_z.jpg?resize=625%2C190" alt="Error: Maximum execution time of 60 seconds exceeded" width="625" height="190" data-recalc-dims="1" /> 

&#8220;<span style="color: #ff0000;"><strong>PHP execution timeout</strong></span>&#8221;

做了一會research 之後找到了解決方法了  
大家可以更改**php.ini**

<pre>max_execution_time = 60
</pre>

或是在 php的function上加上 set\_time\_limit這個程式碼

E.g.

<pre>// Seconds 設定為 0 是無限
$seconds = 60;
set_time_limit($seconds);
</pre>

Happy coding