---
id: 3246
title: 'Restart Apache on Linux &#8211; 如何在Linux 上重新啟動Apache'
date: 2014-06-22T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3246
permalink: '/2014/06/restart-apache-on-linux-%e5%a6%82%e4%bd%95%e5%9c%a8linux-%e4%b8%8a%e9%87%8d%e6%96%b0%e5%95%9f%e5%8b%95apache/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Ubuntu
---
自從自己有了一個**Ubuntu** [**Linux Base**]的**VPS** 之後  
有很多事情都沒有**GUI** 的幫忙..  
他的好處是.令我學會了很多**Linux** 的 Command..  
因為還是新手的關係..所以寫下筆記會方便一點

今天想和大家分享的是

如何在**Linux** 上從重啟動**Apache**?  
每次更新了**Apache**的**Config**後  
E.G. 更改了 **Virtual Host**的內容後  
都需要重新啟動你的**Apache Service**

**解決方法**十分簡單..我們需要使用 **Sudo**的權限 來重新啟動**Apache**的

在**Command Prompt** 上輸入這個Command便可以了

<pre>sudo service apache2 reload
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3898/14605213430_6aa48f0208_z.jpg?resize=625%2C159" alt="Reload Apache service on Linux - sudo service apache2 reload" width="625" height="159" data-recalc-dims="1" /> 

Hope you find it useful