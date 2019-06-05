---
id: 2028
title: 'Could not load file or assembly &#8216;System.Web.Helpers&#8217; / Could not load file or assembly &#8216;System.Web.WebPages.Razor&#8217;'
date: 2011-08-13T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2028
permalink: /2011/08/could-not-load-file-or-assembly-system-web-helpers-could-not-load-file-or-assembly-system-web-webpages-razor/
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC on IIS
---
今天嘗試在朋友的**VPS** 上發佈我的**ASP.Net MVC Sample** 試試看..  
很可惜出現了**Runtime Error**  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d12332d8deba4648aee794d245af0f11/renditions/fullsize.jpg?resize=625%2C244" alt="ASP.Net RunTime Error" width="625" height="244" data-recalc-dims="1" />  
由於詳細的錯誤信息不能在**remote** 看到的關係..  
所以我便用**Remote Desktop 登入 VPS**  
之後在入面瀏覽這個網頁發現了以下的錯誤信息

&#8220;**<span style="color: #ff0000;">Could not load file or assembly &#8216;System.Web.Helpers&#8217;</span>**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ce1f590bf2be49d3acd389ba0fb82986/renditions/fullsize.jpg?resize=625%2C310" alt="Could not load file or assembly 'System.Web.Helpers'" width="625" height="310" data-recalc-dims="1" />  
我嘗試在**Visual Studio**上 把欠缺的 **ddl 設定成Copy To Local = True**  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dfcd64ffce3f46daa57d1114f3becee8/renditions/fullsize.jpg?resize=328%2C259" alt="Reference Copy to Local = true" width="328" height="259" data-recalc-dims="1" />  
之後再發佈到**VPS**上..可惜還是有別的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Could not load file or assembly &#8216;System.Web.WebPages.Razor&#8217;</strong></span>&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4d6b3aec03bf425e9b8d655d4875b75f/renditions/fullsize.jpg?resize=625%2C326" alt="Could not load file or assembly 'System.Web.WebPages.Razor'" width="625" height="326" data-recalc-dims="1" />  
最後終於找到了解決方法

**解決方法**:  
到**ASP.Net WebSite Download ASP.Net MVC 3 Installer**  
 <a title="http://www.asp.net/mvc/mvc3" href="http://www.asp.net/mvc/mvc3" target="_blank">http://www.asp.net/mvc/mvc3</a>  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8e9eef56cc0b4675ac29bddb24802962/renditions/fullsize.jpg?resize=625%2C400" alt="ASP.Net MVC3 Web Site" width="625" height="400" data-recalc-dims="1" /> 

可以到以下網址直接Download  
 <a title="Download ASP.Net MVC 3" href="http://go.microsoft.com/fwlink/?LinkID=208140" target="_blank">http://go.microsoft.com/fwlink/?LinkID=208140</a>

在Server上 Install 了便可以  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/730ed11a0a284847963118a1a2066e83/renditions/fullsize.jpg?resize=559%2C499" alt="Install ASP.Net MVC 3 Tools Update" width="559" height="499" data-recalc-dims="1" />  
Hope you find it useful