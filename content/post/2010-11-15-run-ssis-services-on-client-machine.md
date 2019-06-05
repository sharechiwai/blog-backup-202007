---
id: 931
title: 'Run SSIS Services From Client Machine How to use SSIS WCF Services Part I&#8212;在客戶端中使用SSIS Services 怎樣使用SSIS WCF Services Part I'
date: 2010-11-15T06:00:51+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=931
permalink: /2010/11/run-ssis-services-on-client-machine/
categories:
  - .Net Tips And Tricks
  - CodePlex
  - SSIS
  - SSISServices
  - WCF
  - Web Services
---
今日想在這裡和大家分享怎樣發佈 這個**SSIS WCF Services**  
大家可以到**CodePlex** Download 這個Zip 檔案

[http://ssisservices.codeplex.com/releases](http://ssisservices.codeplex.com/releases "SSIS WCF Services")  
Download 完成後我們可以把檔案解壓縮到一個地方儲存..  
以備一會兒使用

以下這個例子是用Windows 7中的IIS 7.5 來做的  
使用這個**SSIS WCF Services** 的 系統一定要已安裝 **SSIS Services**  
因為我們需要通過這部電腦的 來執行**SSIS Package** 的

首先我們要在設定好IIS&#8230;  
1) 我們可以 以&#8221;**Start**&#8221; -> &#8220;**Control Panel**&#8221; ->&#8221;**Administrative Tools**&#8221; ->&#8221;**Internet Information Services (IIS) Manager**&#8221;  我的這個例子是使用**Windows 7 中的 IIS 7.5** 的

2) 在&#8221; **Default Web Site**&#8221; 中 按右鍵 -> 選擇 ->&#8221;**Add Application&#8230;/加入應用程式**&#8221;  
[<img class="alignnone size-full wp-image-937" title="IISManager" src="https://i2.wp.com/farm6.static.flickr.com/5226/5688437724_40f287f168.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5226/5688437724_40f287f168.jpg)

3) 在&#8221;**Add Application**&#8221; 視窗 填入適當的資料 , &#8220;**Physical Path&#8230;**&#8221; 中選擇之前 &#8220;**SSISServices.zip**&#8221; Download 完成後解壓縮到的地方, 之後按 &#8220;**OK/確定**&#8221;

[<img class="alignnone size-full wp-image-936" title="AddApplicationScreen" src="https://i1.wp.com/farm6.static.flickr.com/5230/5687865773_8e8a7d7ca4.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5230/5687865773_8e8a7d7ca4.jpg)

4) 之後你便可以看到剛剛建立的&#8221;**Web Application**&#8220;, 按一下&#8221;**Content View**&#8221; 分頁

[<img class="alignnone size-full wp-image-934" title="ContentView" src="https://i1.wp.com/farm6.static.flickr.com/5270/5687866683_db5aecd2dc.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5270/5687866683_db5aecd2dc.jpg)

5) 選擇 &#8220;**SSISServices.svc**&#8221; 檔案後, 用右鍵 按一下 &#8220;**Browse/瀏覽**&#8221;

[<img title="ContentView2" src="https://i0.wp.com/farm6.static.flickr.com/5288/5688436482_a87d0a8bc3.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5288/5688436482_a87d0a8bc3.jpg)

6) 之後電腦便會在&#8221;**瀏覽器**&#8220;中把開這個**SSIS WCF web services** 了

[<img class="alignnone size-full wp-image-933" title="SSISServicesIE" src="https://i2.wp.com/farm6.static.flickr.com/5028/5687869103_a1e99a56f9.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5028/5687869103_a1e99a56f9.jpg)

7) 按一下WSDL 連結後便會看到 **WSDL** 的內容了

[<img class="alignnone size-full wp-image-932" title="SSISWSDL" src="https://i1.wp.com/farm6.static.flickr.com/5309/5688438552_ffda194e6e.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5309/5688438552_ffda194e6e.jpg)

之後你便可以把 這個**SSIS WCF Services** 加進到你的 **Project**上使用了

Hope you find it useful