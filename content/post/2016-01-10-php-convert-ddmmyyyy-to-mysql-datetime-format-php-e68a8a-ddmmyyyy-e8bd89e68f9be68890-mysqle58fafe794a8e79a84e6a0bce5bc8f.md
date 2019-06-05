---
id: 3543
title: 'php convert dd/mm/yyyy to mysql datetime format &#8211; PHP 把 dd/mm/yyyy 轉換成 MySQL可用的格式'
date: 2016-01-10T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3543
permalink: '/2016/01/php-convert-ddmmyyyy-to-mysql-datetime-format-php-%e6%8a%8a-ddmmyyyy-%e8%bd%89%e6%8f%9b%e6%88%90-mysql%e5%8f%af%e7%94%a8%e7%9a%84%e6%a0%bc%e5%bc%8f/'
categories:
  - PHP 新手筆記
tags:
  - mysql
  - PHP
  - PHP Troubleshooting
---
今天使用**PHP** 來把一些 **XML Data** 加入 **MySQL** 時出現了一些問題  
原因是那些 **XML**的 **Date Format** 是 **dd/mm/yyyy** 不能直接轉換成 **MySQL**的 **DateTime Format**

**MySQL**的 **Format**要是 **yyyy/mm/dd**  
做了一會research 之後終於找到解決方法了

**PHP** 轉換**Date Format**的功能是  
<span style="color: #339966;"><strong>DateTime::createFromFormat(&#8216;Input Date Format&#8217;, $startDate)->format(&#8216;Y-m-d&#8217;);</strong></span>

<pre>$startDate = '25/12/2015';
  $startDate = DateTime::createFromFormat('d/m/Y', $startDate)-&gt;format('Y-m-d');
</pre>

Happy Coding