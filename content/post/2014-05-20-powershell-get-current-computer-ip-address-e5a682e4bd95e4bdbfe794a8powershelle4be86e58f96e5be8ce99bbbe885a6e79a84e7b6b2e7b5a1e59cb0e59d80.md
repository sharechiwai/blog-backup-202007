---
id: 3190
title: Powershell get Current Computer IP Address – 如何使用Powershell來取後電腦的網絡地址
date: 2014-05-20T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3190
permalink: '/2014/05/powershell-get-current-computer-ip-address-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8powershell%e4%be%86%e5%8f%96%e5%be%8c%e9%9b%bb%e8%85%a6%e7%9a%84%e7%b6%b2%e7%b5%a1%e5%9c%b0%e5%9d%80/'
categories:
  - Powershell
tags:
  - Networking
---
在之前的網誌分享了如何使用**PowerShell**取得本機名稱

### <a href="http://blog.sharechiwai.com/2014/05/powershell-get-current-computer-name-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8powershell%e4%be%86%e5%8f%96%e5%be%8c%e9%9b%bb%e8%85%a6%e5%90%8d%e7%a8%b1/" rel="bookmark">Powershell get Current Computer name – 如何使用Powershell來取後電腦名稱</a> {.entry-title}

今天想和大家分享如何使用**Powershell**來取後電腦的網絡地址

**解決方法**十分簡單  
我們可以使用<span style="color: #008000;"><strong>[System.Net.Dns]::GetHostEntry</strong></span> 的方法 的<span style="color: #008000;"><strong>AddressList</strong> </span>屬性 來取得電腦的網絡地址

**E.G.**

<pre>[System.Net.Dns]::GetHostEntry("ComputerName/電腦名稱").AddressList
</pre>

**本機的網絡地址**

<pre>[System.Net.Dns]::GetHostEntry($env:ComputerName).AddressList
</pre>

<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2911/14397836765_92a35d25cb_z.jpg?resize=625%2C272" alt="Use PowerShell to retrieve Computer's IP Address" width="625" height="272" data-recalc-dims="1" /> 

Hope you find it useful