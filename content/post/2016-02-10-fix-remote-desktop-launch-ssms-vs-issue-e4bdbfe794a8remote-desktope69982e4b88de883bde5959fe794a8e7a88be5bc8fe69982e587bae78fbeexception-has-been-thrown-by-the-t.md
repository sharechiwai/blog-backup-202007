---
id: 3583
title: 'Fix Remote Desktop Launch SSMS VS issue / 使用Remote Desktop時不能啟用程式時出現&#8221;Exception has been thrown by the target of an invocation&#8221;'
date: 2016-02-10T00:00:15+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3583
permalink: '/2016/02/fix-remote-desktop-launch-ssms-vs-issue-%e4%bd%bf%e7%94%a8remote-desktop%e6%99%82%e4%b8%8d%e8%83%bd%e5%95%9f%e7%94%a8%e7%a8%8b%e5%bc%8f%e6%99%82%e5%87%ba%e7%8f%beexception-has-been-thrown-by-the-t/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Remote Desktop
  - Remote Desktop Connection Manager
---
最近使用 Remote Desktop Connection Manager / Remote Desktop時  
發現不能再執行 SQL Server Management Studio /和 Visual Studio  
當執行 **SQL Server Management Studio** (**SSMS**) 時出現  
&#8220;<span style="color: #ff0000;"><strong>Exception has been thrown by the target of an invocation</strong></span>&#8221;  
**Visual Studio** 時出現  
&#8220;<span style="color: #ff0000;"><strong>A problem occurred when loading the Microsoft Visual Studio menu. To fix this problem, run &#8216;devenv.exe /resetsettings&#8217; from the command prompt. Note: this command reset your environment settings</strong></span>&#8221;  
嘗試執行 &#8220;**devenv.exe /resetsettings**&#8221; 也沒有幫助

做了一會**research**之後發現  
原來是 &#8220;Environment Variable&#8221; ->&#8221;**System variable**&#8221; 的&#8221;Path&#8221;過長的關係  
這條Path最多只可以儲存 2048個字元  
長過這個字元便會出現這些錯誤  
解決方法十分簡單  
就是把一些只是自己這個使用者便用的&#8221;Environment Variable&#8221;從 &#8220;System Variable&#8221; 搬到 &#8220;User Variable&#8221;上  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1662/24931047216_294b3204b2_z.jpg?resize=625%2C445" alt="System Variable over 2100 Characters" width="625" height="445" data-recalc-dims="1" />  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1634/24931047346_d56dc0aa82_z.jpg?resize=412%2C467" alt="Environment Variable - User Variable" width="412" height="467" data-recalc-dims="1" />  
之後按 &#8220;OK/確正&#8221; 便可以了

再次連接Remote Desktop 應該便可以正常執行 SSMS / Visual Studio了

Hope you find it useful