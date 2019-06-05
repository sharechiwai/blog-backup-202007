---
id: 2666
title: 'Windows Server 2003 disable IE Enhanced Security &#8211; Internet Explorer Enhanced Security Configuration is enabled'
date: 2013-04-05T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2666
permalink: /2013/04/windows-server-2003-disable-ie-enhanced-security-internet-explorer-enhanced-security-configuration-is-enabled/
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Internet Explorer
  - troubleshooting
---
上次和大家介紹過怎樣在**Windows Server 2008 R2**上解決 &#8220;**Internet Explorer Enhanced Security Configuration is enabled**&#8221; 這個問題  
<a title="Permalink to Windows Server 2008 R2 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled" href="http://blog.sharechiwai.com/2013/04/windows-server-2008-r2-disable-ie-enhanced-security-internet-explorer-enhanced-security-configuration-is-enabled/" rel="bookmark"><br /> Windows Server 2008 R2 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled</a>

今天我要在公司另一個**Server**上做一些測試..  
很可惜..又遇到差不多的問題  
但是這些的系統是**Windows Server 2003  
[<img class="alignnone size-full wp-image-2679" alt="Windows Server 2003 Internet Explorer Enhanced Security Configuration Enabled" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/WinServer2003IEEsc.jpg?resize=625%2C472" width="625" height="472" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/WinServer2003IEEsc.jpg)**  
我嘗試使用差不多的step來解決這個問題..  
很可惜找不到&#8221;**Server Manager**&#8221; 這個東西&#8230;  
做了一會research 之後..  
終於找到了解決方法了

**解決方法**:  
按&#8221;**Start**/**開始**&#8221; menu ->&#8221;**Control Panel**/**控制台**&#8221;  
按下 &#8220;**Add or Remove Programs** /**新增移除程式**&#8221;  
[<img class="alignnone size-full wp-image-2680" alt="Control Panel -> Add / Remove Programs" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/AddRemoveProgram.jpg?resize=615%2C961" width="615" height="961" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/AddRemoveProgram.jpg)  
按下左邊的&#8221;**Add/Remove Windows Components** /**新增移除視窗元件**&#8221;  
[<img class="alignnone size-full wp-image-2681" alt="Add / Remove Programs -> Add / Remove Windows Component" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Win03AddRemoveWindowsComponent.jpg?resize=625%2C459" width="625" height="459" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Win03AddRemoveWindowsComponent.jpg)  
之後找出&#8221;I**nternet Explorer Enhanced Security Configuration**&#8221;  
&#8220;**untick**/**勾去掉**&#8220;&#8221;**Internet Explorer Enhanced Security Configuration**&#8221; 的 &#8220;**checkbox**/**複選框**&#8221;  
[<img class="alignnone size-full wp-image-2682" alt="Windows Server 2003 Components Wizard" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Win03WinComponentsWizard.jpg?resize=512%2C421" width="512" height="421" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Win03WinComponentsWizard.jpg)  
之後按&#8221;**OK**/**確定**&#8221; 便可以了

再次開啟網頁時已經不會再有這些Warning的 Popup了

Hope you find it useful