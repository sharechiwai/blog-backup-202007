---
id: 3600
title: How to start a web server via PHP – 如何使用PHP 來建立一個網絡伺服器?
date: 2016-02-18T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3600
permalink: '/2016/02/how-to-start-a-web-server-via-php-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8php-%e4%be%86%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e7%b6%b2%e7%b5%a1%e4%bc%ba%e6%9c%8d%e5%99%a8/'
categories:
  - PHP 新手筆記
---
之前和大家介紹過怎樣使用**Python** 來建立一個網絡伺服器  
<a href="http://blog.sharechiwai.com/2015/03/how-to-start-a-web-server-via-python-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8python-%e4%be%86%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e7%b6%b2%e7%b5%a1%e4%bc%ba%e6%9c%8d%e5%99%a8/" target="_blank">How to start a web server via Python – 如何使用Python 來建立一個網絡伺服器?</a>

今天再想一想..原來這個指令是十分有用的  
所以便和大家分享 **如何使用PHP 來建立一個網絡伺服器** =P  
之前當要測試一些**PHP** code的時候  
我常常都在 **XAMPP**的 **htdoc** 資料夾內建立新的資料夾 來試東西

現在只需要使用**Command Prompt**開啟這個要測試**PHP** Code的資料來  
之後 執行以下**PHP** 指令便可以輕鬆地起一個**Web Server**了

<pre>php -S localhost:8080
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1703/24524452153_85e259a468_z.jpg?resize=625%2C140" alt="PHP command to build web server" width="625" height="140" data-recalc-dims="1" />  
之後大家便可以到 **http://localhost:8080** 去看看 PHP Code做了什麼出來

Hope you find it useful