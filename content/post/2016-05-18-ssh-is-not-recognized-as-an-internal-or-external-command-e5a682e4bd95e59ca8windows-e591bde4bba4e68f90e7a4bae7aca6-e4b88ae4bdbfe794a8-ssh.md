---
id: 3668
title: '&#8216;ssh&#8217; is not recognized as an internal or external command &#8211; 如何在Windows 命令提示符 上使用 SSH'
date: 2016-05-18T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3668
permalink: '/2016/05/ssh-is-not-recognized-as-an-internal-or-external-command-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e5%91%bd%e4%bb%a4%e6%8f%90%e7%a4%ba%e7%ac%a6-%e4%b8%8a%e4%bd%bf%e7%94%a8-ssh/'
categories:
  - .Net Tips And Tricks
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Git
  - SSH
  - Windows
---
很多時候網上的教學都是使用**Linux** 或 **Mac**的**Bash**  
有很多時候都會使用到**SSH**

最近嘗試在**Windows 的Command Prompt**上使用 **SSH**時出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>&#8216;ssh&#8217; is not recognized as an internalor external command, operable program or batch file</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7484/26583243853_9fa3efe056_z.jpg?resize=625%2C128" alt="SSH is not recognized " width="625" height="128" data-recalc-dims="1" /> 

如何可以在Windows 命令提示符 上使用 **SSH**呢  
解決方法十分簡單  
相信很多Developer都有使用**Git**的  
如果唔有的話可以到以下網址 下載及安裝**Git**  
<https://git-scm.com/downloads>

安裝完成後..便可以在**Windows** 的 **Environment Path** **環境變數**上的 &#8220;**Path**&#8220;變數上加上  
<span style="color: #008000;"><strong>Git\usr\bin</strong></span> 的路徑  
因為這個路徑上存有很多有用的工具/程式  
E.G  
<span style="color: #008000;"><strong>C:\Program Files\Git\usr\bin<br /> <img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7520/26913335540_df8d7caed7_z.jpg?resize=625%2C220" alt="Git User Bin Path" width="625" height="220" data-recalc-dims="1" /><br /> </strong></span>

按下&#8221;**確定**&#8220;便可以了  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7645/27154825246_38d8b57616_z.jpg?resize=574%2C640" alt="Add Environment Variable on Windows 10 for Git User Bin" width="574" height="640" data-recalc-dims="1" /> 

之後當我們在**Windows** 的 **Command prompt**上執行 **SSH**了  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7721/26583243773_c597e0288c_z.jpg?resize=625%2C175" alt="Successfully Run SSH on Windows" width="625" height="175" data-recalc-dims="1" />  
Hope you find it useful