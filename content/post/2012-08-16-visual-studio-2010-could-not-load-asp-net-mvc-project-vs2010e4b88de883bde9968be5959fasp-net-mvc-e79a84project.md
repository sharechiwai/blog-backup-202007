---
id: 2551
title: 'Visual Studio 2010 Could not load ASP.Net MVC Project &#8211; VS2010不能開啟ASP.Net MVC 的Project'
date: 2012-08-16T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2551
permalink: '/2012/08/visual-studio-2010-could-not-load-asp-net-mvc-project-vs2010%e4%b8%8d%e8%83%bd%e9%96%8b%e5%95%9fasp-net-mvc-%e7%9a%84project/'
categories:
  - ASP.Net MVC
tags:
  - Visual Studio 2010
---
今天同事開始學習寫**ASP.Net MVC 3**的Website  
希望當我在放假時公司的網頁有**Bugs**或需要加新功能時  
他也可以嘗試去解決問題

誰不知..當他從**TFS** 取後**Project**卻出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>One or more projects in the solution were not loaded correctly. Please see te Output Windows for details</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/463bdb90b40746a28f0a268935a7e305" alt="One or more projects in the solution were not loaded correctly. Please see te Output Windows for details" width="490" height="241" /> 

當我查看 &#8220;**Output Windows**/**輸出視窗**&#8221; 時出現了以下的信息  
&#8220;<span style="color: #ff0000;"><strong>The project type is not supported by this installation.</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/aff9c7e8bbd840cf8efbf99c92b6b45f" alt="The project type is not supported by this installation." width="523" height="116" />  
其他原因很簡單..  
是因為他沒有在電腦上安裝ASP.Net MVC3的元件  
**解決方法**:  
大家可以到**ASP.Net** 的網頁上**Download**.  
<a title="ASP.Net MVC3 Download" href="http://www.asp.net/mvc/mvc3" target="_blank">http://www.asp.net/mvc/mvc3</a>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/93fa640f94cf4a969a5a64004c8769ac" alt="ASP.Net Website Download ASP.Net MVC" width="646" height="466" />  
之後開啟安裝便可以了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2754db8f1dd1434b968fa43e73e1091e" alt="Install ASP.Net MVC 3 via Web PI" width="923" height="628" />  
Happy Coding