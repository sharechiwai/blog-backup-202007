---
id: 2468
title: '&#8216;jQuery 1.7.2&#8217; installed. Conflict occurred. &#8216;jQuery1.51.&#8217; referenced but requested &#8216;jQuery 1.7.2&#8217;. &#8216;jQuery.vsdoc.1.5.1, jQuery.Validation.1.8.0, jQuery.UI.Combined 1.8.11&#8217; depend on &#8216;jQuery 1.5.1&#8217;.'
date: 2012-05-12T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2468
permalink: /2012/05/jquery-1-7-2-installed-conflict-occurred-jquery1-51-referenced-but-requested-jquery-1-7-2-jquery-vsdoc-1-5-1-jquery-validation-1-8-0-jquery-ui-combined-1-8-11-depend-on-jquery/
categories:
  - NuGet
tags:
  - JQuery Conflict occurred
---
每當我開始一個新**Project**的時候我都會使用**NuGet Package Manager**  
&#8220;**Tools**&#8221; ->&#8221;**Library Package Manager**&#8221; -> 選擇 &#8220;**Add Library Package Reference&#8230;**&#8221;  
按一下&#8221;**Update**&#8220;分頁  
去檢查一下Project上已安裝的**Package**/**Reference**..  
是不是最新的&#8230;  
如果不是的話&#8230;會使用&#8221;Update&#8221; 按鈕 來把他們更新到最新的..  
以減輕有**BUG**/安全的問題

當我嘗試更新 **jQuery 1.51**. 到**jQuery 1.7.2**的時候&#8230;  
**NuGet**彈出了一個錯誤信息&#8230;  
&#8220;&#8216;<span style="color: #ff0000;"><strong>jQuery 1.7.2&#8242; installed. Conflict occurred. &#8216;jQuery1.51.&#8217; referenced but requested &#8216;jQuery 1.7.2&#8217;. &#8216;jQuery.vsdoc.1.5.1, jQuery.Validation.1.8.0, jQuery.UI.Combined 1.8.11&#8217; depend on &#8216;jQuery 1.5.1&#8217;.</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/91fffaa8472f4ad3b3c987d80e78d37c" width="881" height="483" alt="jQuery 1.7.2' installed. Conflict occurred. 'jQuery1.51.' referenced but requested 'jQuery 1.7.2'. 'jQuery.vsdoc.1.5.1, jQuery.Validation.1.8.0, jQuery.UI.Combined 1.8.11' depend on 'jQuery 1.5.1'" />  
其實是因為有其他的檔案是**Reference**到舊的 **JQuery** 檔案上所以造成的&#8230;  
**解決方法**十分簡單..  
大家先要把所有和**JQuery** 相關的 **Reference**先進行更新便可以了  
最後才更新 **JQuery** 的檔案..

Hope you find it useful.