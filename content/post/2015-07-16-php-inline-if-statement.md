---
id: 3444
title: PHP Inline If Statement
date: 2015-07-16T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3444
permalink: /2015/07/php-inline-if-statement/
categories:
  - PHP 新手筆記
tags:
  - Best Practices
  - PHP
---
有時在使用**InLine** **If Statement** 感覺上方便很多  
還可以增加可讀性

怎樣在**PHP**上使用 **inline If Statement**呢

其實是十分簡單的  
他們的組合是這樣的 &#8220;**? :**&#8221;  
<span style="color: #339966;"><strong>condition</strong> </span>? <span style="color: #0000ff;"><strong>true</strong> </span>: <span style="color: #ff0000;"><strong>false</strong></span>;

E.g

<pre>echo  1==2 ? "true" : "false";

// 結果會輸出 "false"的
</pre>

Hope you find it useful