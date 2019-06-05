---
id: 3404
title: 'Python &#8211; No Module named SimpledHTTPServer'
date: 2015-03-20T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3404
permalink: /2015/03/python-no-module-named-simpledhttpserver/
categories:
  - Python
tags:
  - Python Troubleshooting
---
之前介紹了大家怎樣可以使用**Python來建立一個網絡伺服器**  
[How to start a web server via Python – 如何使用Python 來建立一個網絡伺服器?](http://blog.sharechiwai.com/2015/03/how-to-start-a-web-server-via-python-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8python-%e4%be%86%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e7%b6%b2%e7%b5%a1%e4%bc%ba%e6%9c%8d%e5%99%a8/ "How to start a web server via Python – 如何使用Python 來建立一個網絡伺服器?")

有朋友說當他們執行這指令

<pre>python -m SimpleHTTPServer
</pre>

之後出現以下的錯誤信息..  
&#8220;<span style="color: #ff0000;"><strong>No Module named SimpledHTTPServer</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8733/16358918114_ea11d6f09f_z.jpg?resize=625%2C299" alt="Python - No Module named SimpleHTTPServer" width="625" height="299" data-recalc-dims="1" /> 

這可能是系統或版權所有的問題吧

**解決方法**十分簡單  
大家可以嘗試使用以下指令

<pre>python -m http.server
</pre>

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7611/16793826960_573c23d972_z.jpg?resize=624%2C359" alt="Python Web Server Up and running via python -m http.server command" width="624" height="359" data-recalc-dims="1" /> 

應該可以解決這個問題的  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7648/16773907647_039aa7a93b_z.jpg?resize=297%2C136" alt="Python Web server is up and running" width="297" height="136" data-recalc-dims="1" /> 

Hope you find it useful