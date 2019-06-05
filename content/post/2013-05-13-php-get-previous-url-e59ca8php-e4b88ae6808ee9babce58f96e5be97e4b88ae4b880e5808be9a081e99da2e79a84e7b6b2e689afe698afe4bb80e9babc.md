---
id: 2867
title: 'PHP Get Previous URL &#8211; 在PHP 上怎麼取得上一個頁面的網扯是什麼'
date: 2013-05-13T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2867
permalink: '/2013/05/php-get-previous-url-%e5%9c%a8php-%e4%b8%8a%e6%80%8e%e9%ba%bc%e5%8f%96%e5%be%97%e4%b8%8a%e4%b8%80%e5%80%8b%e9%a0%81%e9%9d%a2%e7%9a%84%e7%b6%b2%e6%89%af%e6%98%af%e4%bb%80%e9%ba%bc/'
categories:
  - PHP 新手筆記
---
有時候我們需要找到用戶是從那一個頁面/網址來到這一頁的  
這可以方便大家可能要使用者到某一個頁面去做一些Process  
之後**Redirect** 回之前的一個頁面

**解決方法**

我使可以使用以下的 **PHP** Code

[php]  
$\_SERVER[&#8216;HTTP\_REFERER&#8217;];  
[/php]

Hope you find it useful