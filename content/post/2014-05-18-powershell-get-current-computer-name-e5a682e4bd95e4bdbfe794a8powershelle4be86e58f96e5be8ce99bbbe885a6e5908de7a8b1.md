---
id: 3187
title: 'Powershell get Current Computer name &#8211; 如何使用Powershell來取後電腦名稱'
date: 2014-05-18T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3187
permalink: '/2014/05/powershell-get-current-computer-name-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8powershell%e4%be%86%e5%8f%96%e5%be%8c%e9%9b%bb%e8%85%a6%e5%90%8d%e7%a8%b1/'
categories:
  - Powershell
---
開始學習使用**Powershell**..  
首先學習一些很基本的的 **Command**  
如何使用**Powershell**來取後電腦名稱

解決方法十分簡單

我們可以使用以下的 **Powershell Command** 便可以了

<pre>[System.Net.Dns]::GetHostName()
</pre>

或

<pre>$env:COMPUTERNAME
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3888/14411790513_7765082a95_z.jpg?resize=581%2C149" alt="Powershell Get Current Computer Name" width="581" height="149" data-recalc-dims="1" /> 

Hope you find it useful