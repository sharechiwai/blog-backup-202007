---
id: 3148
title: 'PHP Concatenate String Array &#8211; PHP 字符串連接'
date: 2014-04-20T00:00:43+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3148
permalink: '/2014/04/php-concatenate-string-array-php-%e5%ad%97%e7%ac%a6%e4%b8%b2%e9%80%a3%e6%8e%a5/'
categories:
  - PHP 新手筆記
---
有時候你可能需要把很多的字串變數和 文字連接在一起  
如果我們使用 &#8220;**.**&#8220;.. 有時候會令人感到混亂

當遇到這個情況時  
大家可以嘗試使用 **join** 這個**PHP** 功能去**Concat String**

**E.G.**

[php]  
$httpheader = "http://";  
$com = ".com;  
$page = "/albums;

$string = array($httpheader,&#8217;sharechiwai&#8217;,$com,$page);

echo join("",$string);  
// <strong>http://sharechiwai.com/albums</strong>  
[/php]

或者在連接中間加入一些字串

[php]  
echo join("-",$string);  
// <strong>http://-sharechiwai-.com-/albums</strong>  
[/php]

Hope you find it useful