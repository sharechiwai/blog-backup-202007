---
id: 3746
title: 'Linux Note &#8211; Ubuntu Remove Nginx'
date: 2016-07-12T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3746
permalink: /2016/07/linux-note-ubuntu-remove-nginx/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - Nginx
  - Ubuntu
---
今日嘗試做**Nginx Reverse Proxy Lookup** 出現了問題..  
令到網頁一開便出現**Nginx**的 information..  
原先的網頁消失了..  
所以要快快 **remove nginx** 去待網頁正常運作

**解決方法**十分簡單..  
我們只需要執行以下指令便可以了

<pre>sudo apt-get remove nginx nginx-common
</pre>

Hope you find it useful