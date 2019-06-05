---
id: 3690
title: 'Linux/Ubuntu &#8211; check which port is open &#8211; 如何檢查在Ubuntu/Linux 上那些Port Open了呢'
date: 2016-07-03T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3690
permalink: '/2016/07/linuxubuntu-check-which-port-is-open-%e5%a6%82%e4%bd%95%e6%aa%a2%e6%9f%a5%e5%9c%a8ubuntulinux-%e4%b8%8a%e9%82%a3%e4%ba%9bport-open%e4%ba%86%e5%91%a2/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - Microsoft Azure
  - Ubuntu
  - Windows Azure
---
之前和大家分享過 使用[Azure Free Tier 的MySQL Database 有Connection Limitation的問題](http://blog.sharechiwai.com/2016/05/azure-failed-with-message-user-has-exceeded-the-max_user_connections-resource-current-value-4/)  
之後便做了一會research 看看有沒有些比較 cost effective 的alternative  
做了半天的research都找不到想要的東西..  
最後便決定自己在**Azure** 上起一個**Development Server** 方便和朋友試東西

覺得自己已經把**End Point**設定好..  
但是不知道為什麼在Server之外嘗試檢查 port 3306有沒有開放..  
還是close的&#8230;

但是使用網上的工具去檢查時發現 **Port 3306** 是Close的  
E.G.  
[http://sharechiwai.com/networktools  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7353/27957698200_9b851f2c4c_z.jpg?resize=625%2C438" alt="Check which port is open Online" width="625" height="438" data-recalc-dims="1" />  
](http://sharechiwai.com/networktools) 

所以便需要看看其實 **Ubuntu**/**Linux** 內有沒有 **開放/Listen port 3306**了  
那麼..如何檢查在**Ubuntu**/**Linux** 上那些**Port Open**了呢?

**解決方法**  
我們可以在**Terminial** 上執行這個指令

<pre>netstat -ntlp | grep LISTEN
</pre>

他便會列出**Linux**/ **Ubuntu正在Listen那些Port**了  
E.G. 那些Port是open的  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7409/27957943750_543c15246b_z.jpg?resize=625%2C370" alt="Linux check which port is open" width="625" height="370" data-recalc-dims="1" /> 

Hope you find it useful