---
id: 1929
title: 'Validate HTML5 Sytax on Visual Studio &#8211; Visual Studio上驗証 HTML5'
date: 2011-07-26T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1929
permalink: '/2011/07/validate-html5-sytax-on-visual-studio-visual-studio%e4%b8%8a%e9%a9%97%e8%a8%bc-html5/'
categories:
  - ASP.Net MVC
tags:
  - HTML5
  - Validate HTML5
---
當我們在**Visual Studio 2010** 上建立**ASP.Net MVC Application**時  
**Visual Studio** 會自動產生一些檔案  
當我嘗試打開 **_Layout.cshtml**修改時 [這一個檔案就像 **ASP.Net Application** 上的**Master Page** 差不多]  
之後發現.. 有很多green line ->[說明了有些Code 是有Warning..不能通過驗證]  
&#8220;<span style="color: #ff0000;"><strong>Validation (XHTML 1.1): Attribute &#8216;charset&#8217; is not a valid attribute of element &#8216;meta&#8217;</strong></span>&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/244830ba2bf74bc68fc3dc6f4043de65/renditions/fullsize.jpg?resize=501%2C240" alt="" width="501" height="240" data-recalc-dims="1" /> 

<img title="Validation (XHTML 1.1): Attribute 'charset' is not a valid attribute of element 'meta'" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2b173ea20a984edcadfbc542b23d65a4/renditions/fullsize.jpg?resize=625%2C170" alt="Validation (XHTML 1.1): Attribute 'charset' is not a valid attribute of element 'meta'" width="625" height="170" data-recalc-dims="1" /> 

之後發現原來預設的**ASP.Net MVC** 的Markup 是用**HTML5**的..  
而預設的**Visual Studio 2010的預設HTML 驗證是 XHTML1.1**.  
解決方法只是把 **Visual Studio** 的**預設的HTML Validator轉成HTML5** 便可以了

**解決方法**:  
按&#8221;**工具列/Tools**&#8221; ->&#8221;**選項/Options**&#8221;  
<img title="Visual Studio 2010 Tools Options" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/557607f626fc453382722d371fbc6407/renditions/fullsize.jpg?resize=440%2C426" alt="Visual Studio 2010 Tools Options" width="440" height="426" data-recalc-dims="1" />  
在&#8221;**選項/Options dialog**” 上選擇&#8221;**文字處理器/Text Editor**&#8221; ->選擇 &#8220;**HTML**&#8221; ->&#8221;**驗證/Validation**&#8221;  
之後在&#8221;**目標/Target**&#8221; 上選擇&#8221;**HTML5**&#8221; 便可以了  
<img title="Validate HTML5 Sytax on Visual Studio - Visual Studio上驗証 HTML5 " src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a55df87c188b4f2dadc2299f73f4f0ca/renditions/fullsize.jpg?resize=625%2C366" alt="Validate HTML5 Sytax on Visual Studio - Visual Studio上驗証 HTML5 " width="625" height="366" data-recalc-dims="1" />  
Hope you find it useful