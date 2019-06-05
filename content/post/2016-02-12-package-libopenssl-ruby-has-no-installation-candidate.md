---
id: 3592
title: 'Package &#8216;libopenssl-ruby&#8217; has no installation candidate'
date: 2016-02-12T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3592
permalink: /2016/02/package-libopenssl-ruby-has-no-installation-candidate/
categories:
  - Linux Notes / Linux 新手筆記
  - UBuntu
tags:
  - Ubuntu
  - WPScan
---
今日嘗試跟隨**Digital Ocean** 的教學  
去安裝**WPScan** 來檢查一下自己的**WordPress**有沒有什麼問題  
<a href="https://www.digitalocean.com/community/tutorials/how-to-use-wpscan-to-test-for-vulnerable-plugins-and-themes-in-wordpress" target="_blank">https://www.digitalocean.com/community/tutorials/how-to-use-wpscan-to-test-for-vulnerable-plugins-and-themes-in-wordpress</a>

當我使用以下指令到安裝**WPScan**的**dependencies** 時

<pre>sudo apt-get install libcurl4-gnutls-dev libopenssl-ruby libxml2 libxml2-dev libxslt1-dev ruby-dev ruby1.9.3
</pre>

可惜出現以下錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Package &#8216;libopenssl-ruby&#8217; has no installation candidate</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1526/24924099011_8f1e8aa455_z.jpg?resize=625%2C167" alt="Package 'libopenssl-ruby' has no installation candidate" width="625" height="167" data-recalc-dims="1" /> 

做了一會research之後發現

原因是在 **Ubuntu 14.04**開始**libopenssl-ruby** 已經包括在&#8217;**libruby1.9.1**&#8216;內 所以不用安裝了

我們可以執行以下指令到安裝 **WPScan的 dependencies**

<pre>sudo apt-get install libcurl4-gnutls-dev libxml2 libxml2-dev libxslt1-dev ruby-dev 
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1483/24390554433_bdd0b14023_z.jpg?resize=625%2C370" alt="Install WPScan dependencies" width="625" height="370" data-recalc-dims="1" />  
詳情可以參教 **WPScan**的 Offical site

<a href="https://github.com/wpscanteam/wpscan" target="_blank">https://github.com/wpscanteam/wpscan</a>

Hope you find it useful