---
id: 3193
title: 'PowerShell Get Computer Name by IP Address &#8211; 如何使用Powershell以電腦的網絡地址取得電腦名稱'
date: 2014-05-22T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3193
permalink: '/2014/05/powershell-get-computer-name-by-ip-address-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8powershell%e4%bb%a5%e9%9b%bb%e8%85%a6%e7%9a%84%e7%b6%b2%e7%b5%a1%e5%9c%b0%e5%9d%80%e5%8f%96%e5%be%97%e9%9b%bb%e8%85%a6/'
categories:
  - Powershell
tags:
  - Networking
---
今天需要幫客戶服務同事解決電腦問題  
嘗試叫他提供他的電腦名稱..以方便以**Admin** 權限去 **Remote Access**他的電腦硬碟..  
有機會介紹大家可以怎樣以**Admin** 權限去** Remote Access**其他的電腦硬碟  
很可惜..他對電腦不太認識..所以怎樣教他也不懂得怎樣找出他的電腦名稱..  
幸好公司的一個程式有記下電腦的**Username**和 **IP Address**

最後我使使用了**PowerShell** 以電腦的網絡地址取得電腦名稱

如何使用**Powershell**以電腦的網絡地址取得電腦名稱

**解決方法**  
我們可以使用 <span style="color: rgb(0, 128, 0);"><strong>[System.Net.Dns]::GetHostEntry</strong> </span>功能上的 <span style="color: rgb(0, 128, 0);"><strong>HostName</strong></span> 屬性 來以電腦的網絡地址取得電腦名稱

<pre>[System.Net.Dns]::GetHostEntry('IP Address').HostName
</pre>

E.G.

<pre>[System.Net.Dns]::GetHostEntry('192.168.0.2').HostName
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3872/14211214228_731a8f8387_z.jpg?resize=625%2C67" alt="PowerShell get Computer Name via IP Address" width="625" height="67" data-recalc-dims="1" /> 

Hope you find it useful