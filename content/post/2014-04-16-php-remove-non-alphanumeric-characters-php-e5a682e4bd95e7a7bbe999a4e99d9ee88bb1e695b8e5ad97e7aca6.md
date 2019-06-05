---
id: 3141
title: 'PHP remove Non-Alphanumeric Characters &#8211; PHP 如何移除非英數字符'
date: 2014-04-16T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3141
permalink: '/2014/04/php-remove-non-alphanumeric-characters-php-%e5%a6%82%e4%bd%95%e7%a7%bb%e9%99%a4%e9%9d%9e%e8%8b%b1%e6%95%b8%e5%ad%97%e7%ac%a6/'
categories:
  - PHP 新手筆記
tags:
  - Regex
  - Regular Expression
---
在PHP上 如何移除非英數字符  
我們可以使用**Regular Expression** 來解決這個問題

<pre><strong>[^A-Za-z0-9 ]</strong></pre>

這個**Regular Expression**的規則是用來選擇出非英文數字和空格的字串找出來.之後用Empty String來取代

E.G.

[php]  
$input = "How Are you? 你好嗎? ShareChiWai";

echo "Original Input:";  
echo "<br/>";  
echo $input;  
echo "<br/>";

echo "Removed Non-Alphanumeric Characters Input:";  
echo "<br/>";  
"/[^A-Za-z0-9 ]/", &#8221;, $input);  
[/php]

**Demo:**  
<a title="PHP Remove Non-alphanumeric Characters" href="http://sharechiwai.com/phpdemo/non_alphanumeric_chars_filter" target="_blank">http://sharechiwai.com/phpdemo/non_alphanumeric_chars_filter</a>

<img class="alignnone" src="https://i1.wp.com/farm8.staticflickr.com/7345/14132187043_23e9e70f07_d.jpg?resize=500%2C142" alt="PHP Remove Non Alphanumberic Characters" width="500" height="142" data-recalc-dims="1" />  
Hope you find it useful