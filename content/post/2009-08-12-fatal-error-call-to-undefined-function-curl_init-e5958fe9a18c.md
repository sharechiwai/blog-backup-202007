---
id: 383
title: 'Fatal error: Call to undefined function curl_init() 問題'
date: 2009-08-12T08:12:00+08:00
author: ShareChiWai
layout: post
guid: 'http://sharechiwai.wordpress.com/2009/08/12/fatal-error-call-to-undefined-function-curl_init-%e5%95%8f%e9%a1%8c'
permalink: '/2009/08/fatal-error-call-to-undefined-function-curl_init-%e5%95%8f%e9%a1%8c/'
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "1694680834095947366"
categories:
  - PHP 新手筆記
---
今天想嘗試使用 <span style="font-weight:bold;">CURL </span>這個MODULE去 POST 一些XML Data 到另一個website,  
當我跟著網上的example 試code的時候&#8230;

<span style="font-weight:bold;color:rgb(255,0,0);font-size:85%;"><?</span>  
    <span style="color:rgb(255,0,0);">$ch = <span style="color:rgb(0,0,255);">curl_init()</span>;<br /><span style="color:rgb(255,0,0);">?></span><br />下面的error 便出現了<br /><b>Fatal error</b><span style="color:rgb(255,0,0);">: Call to undefined function curl_init() in </span><b>D:WebServerWebSitePostXML.php</b><span style="color:rgb(255,0,0);"> on line </span><b>8</b></span>

其實解決方法很簡單  
只要到 &#8220;**Notepad**&#8221; 開啟 &#8220;**php.ini**&#8220;  
之後用 &#8220;**Edit**&#8221; ->&#8221;**Find&#8230;**&#8221; 或 <span style="font-weight:bold;">CTRL </span>+ &#8220;<span style="font-weight:bold;">F</span>&#8220;  
找 &#8220;**curl**&#8220;  
你便會找到  
_;extension=php_curl.dll_

你只需要刪除&#8221;<span style="font-weight:bold;color:rgb(51,204,0);">;</span>&#8220;  
之後儲存檔案  
<span style="font-weight:bold;">&#8220;Restart&#8221; </span>你的web server 便可

Good Luck