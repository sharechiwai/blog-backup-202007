---
id: 3409
title: Restart Computer via PowerShell 如何使用PowerShell 來重啟電腦
date: 2015-03-22T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3409
permalink: '/2015/03/restart-computer-via-powershell-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8powershell-%e4%be%86%e9%87%8d%e5%95%9f%e9%9b%bb%e8%85%a6/'
categories:
  - Powershell
tags:
  - TFS Server
  - Windows Server 2012
---
今天公司的**TFS Server**出現了問題  
這個 **TFS Server** 是在一個 安裝了 **Windows Server 2012** 的 **Virtual Machine**上  
不知道為什麼找不到 右手邊的 **menu**..  
最重便想到使用**Powershell** 來重啟這部電腦了

**解決方法**十分簡單

我們只要開啟**PowerShell** 之後輸入 以下指令便可

<pre>Restart-Computer
</pre>

<img class="alignnone" src="https://i2.wp.com/farm9.static.flickr.com/8718/16962746576_29cb09bfcc_z.jpg?resize=625%2C234" alt="PowerShell Restart-Computer command" width="625" height="234" data-recalc-dims="1" /> 

或者可以使用以下指令重啟在網絡上的其他電腦  
我們只需要使用以下  
以下的指令會重啟 ShareChiWaiWebServer 和 ShareChiWaiDBServer

<pre>Restart-Computer -ComputerName ShareChiWaiWebServer, ShareChiWaiDBServer
</pre>

Hope you find it useful