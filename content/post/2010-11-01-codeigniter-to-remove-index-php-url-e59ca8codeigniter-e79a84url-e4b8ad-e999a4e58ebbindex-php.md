---
id: 859
title: 'Codeigniter to remove index.php URL &#8211; 在Codeigniter 的URL 除去index.php'
date: 2010-11-01T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=859
permalink: '/2010/11/codeigniter-to-remove-index-php-url-%e5%9c%a8codeigniter-%e7%9a%84url-%e4%b8%ad-%e9%99%a4%e5%8e%bbindex-php/'
categories:
  - PHP 新手筆記
---
最近朋友介紹了我使用一個十分好用的 **PHP Framework Codeignite**r  
這個Framework 建立出來的Website是用**Model &#8211; View &#8211; Controller** (**MVC**)的 模式的  
有很多很方便的**Helper Class/ Library/ Plugin** 令你可以更快/更有效率地建立一個Website

我也開始學習使用了 =)

今日想和大家分享的是如何 在 **Codeigniter** 的URL 中 除去index.php  
相信對一些對**URL Rewrite** 有經驗的朋友 應該是沒有難度的

我不太懂URL Rewrtie/或 Regular Expression,  
所以我找了朋友幫忙 =)

**方法很簡單**  
只需要在 **Root Folder** 上建立一個 .htaccess檔案  
放入以下內容使可  
[sourcecode language=&#8221;php&#8221;]  
RewriteEngine on

RewriteCond $1 !^(index.php)  
RewriteCond %{REQUEST_FILENAME} !-f  
RewriteCond %{REQUEST_FILENAME} !-d  
RewriteRule ^(.*)$ index.php/$1 [L,QSA]  
[/sourcecode]

Hope you find it useful