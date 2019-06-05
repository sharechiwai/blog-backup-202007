---
id: 3710
title: 'Ubuntu Notes &#8211; How to restart Apache'
date: 2016-08-01T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3710
permalink: /2016/08/ubuntu-notes-how-to-restart-apache/
categories:
  - UBuntu
tags:
  - Apache
  - Ubuntu
---
**小小筆記.**. 方便安裝/設定 Server 時用的..有是Web Server Crash了也可以自行解決

不同版本的 **Ubuntu** 有不同**restart apache 的指令**

**Ubuntu 14.04**

<pre>sudo service apache2 restart
</pre>

或者可以用以下指令到reload 設定

<pre>sudo service apache2 reload
</pre>

**Ubuntu 16.04**

<pre>sudo systemctl restart apache2
</pre>

Hope you find it useful