---
id: 2635
title: 'Asp.net website did not work on ie10 FIXED &#8211; 用戶使用IE10在不能登入ASP.Net 的網頁 SCRIPT5009P &#8216;__doPostBack&#8217; is undefined'
date: 2013-01-03T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2635
permalink: '/2013/01/asp-net-website-did-not-work-on-ie10-fixed-%e7%94%a8%e6%88%b6%e4%bd%bf%e7%94%a8ie10%e5%9c%a8%e4%b8%8d%e8%83%bd%e7%99%bb%e5%85%a5asp-net-%e7%9a%84%e7%b6%b2%e9%a0%81-script5009p-__dopostback-is-un/'
categories:
  - ASP.Net MVC
tags:
  - IIS
  - "SCRIPT5009P '__doPostBack' is undefined"
---
今天有客戶投訢當他們更新了他們的**IE** 到 **IE10**之後 不能登入到公司的ASP.Net 網頁  
之後我便去嘗試是客戶的電腦問題..還是真的是IE10的問題呢  
當我便用**IE10** 去登入公司的網頁時&#8230; 在**Developer Tool** 的**Console**上出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>SCRIPT5009P &#8216;__doPostBack&#8217; is undefined</strong></span>&#8221;  
<a href="http://s1255.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/Script5009.jpg.html" target="_blank"><img alt="SCRIPT5009P '__doPostBack' is undefined" src="https://i2.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/Script5009.jpg?w=625" border="0" data-recalc-dims="1" /></a>

做了一會兒research 之後終生找到了解決方法

**解決方法**:  
我們可以到以下的URL 去Request 這一個**Hotfix**  
&#8220;**A hotfix is available for the ASP.NET browser definition files in the Microsoft .NET Framework 4.0**&#8221;  
<a title="A hotfix is available for the ASP.NET browser definition files in the Microsoft .NET Framework 4.0" href="http://support.microsoft.com/kb/2600088" target="_blank">http://support.microsoft.com/kb/2600088</a>

這個HotFix只可以在以下的系統上應用的  
**.NET Framework 4.0 &#8211; Windows XP, Windows 2003, Windows Vista, Windows Server 2008, Win7, Windows Server 2008 R2 (MSI)**

按了&#8221;**Hotfix Download Available**&#8220;之後便會轉到另外一個頁面..  
<a href="http://s1255.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/AhotfixisavailablefortheASPNETbrowserdefinitionfilesintheMicrosoftNETFramework40-GoogleChrome.jpg.html" target="_blank"><img alt="A hotfix is available for the ASP.NET browser definition files in the Microsoft .NET Framework 4.0" src="https://i0.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/AhotfixisavailablefortheASPNETbrowserdefinitionfilesintheMicrosoftNETFramework40-GoogleChrome.jpg?w=625" border="0" data-recalc-dims="1" /></a>  
填上電郵..之後便會把Hotfix的Download Link發送到你的電郵..  
<a href="http://s1255.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/HotFix2600088.jpg.html" target="_blank"><img alt=" photo HotFix2600088.jpg" src="https://i2.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/HotFix2600088.jpg?w=625" border="0" data-recalc-dims="1" /></a>  
下載安裝後..需要從新啟動電腦才可以Apply這一個**HotFix**

Hope you find it useful