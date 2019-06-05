---
id: 3402
title: 'How to start a web server via Python &#8211; 如何使用Python 來建立一個網絡伺服器?'
date: 2015-03-15T00:00:20+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3402
permalink: '/2015/03/how-to-start-a-web-server-via-python-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8python-%e4%be%86%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e7%b6%b2%e7%b5%a1%e4%bc%ba%e6%9c%8d%e5%99%a8/'
categories:
  - Python
tags:
  - Web Server
---
今天在一個**HTML5 Game Development** 的Workshop上  
學會了如何使用**Python** 來作一個Web Server  
有安裝 **Python**的朋友可以試試

首先大家需要使用 **Command Prompt** 去 輸入 到你**想顯示網頁的資料夾路徑**  
之後輸入以下指令便可以了

<pre>python -m SimpleHTTPServer
</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7654/16773907627_ba3c1a3aa1_z.jpg?resize=595%2C265" alt="Python Web Server - python -m SimpleHTTPServer" width="595" height="265" data-recalc-dims="1" />  
之後大家便可以瀏覽 <a title="Localhost" href="http://localhost:8000" target="_blank">http://localhost:8000</a>  
**port 8000**是這個指令的 **default port number**

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7648/16773907647_039aa7a93b_z.jpg?resize=297%2C136" alt="Python web server" width="297" height="136" data-recalc-dims="1" /> 

如果大家想使用不同的 **port number** 可以在指令尾端加上想要的**port**  
E.g.

<pre>python -m SimpleHTTPServer 8080
</pre>

Hope you find it useful