---
id: 2650
title: 'TFS 2012 SharePoint 2013 Integration Series &#8211;  TFS 2012 SharePoint 2013 整合 前言'
date: 2013-05-01T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2650
permalink: '/2013/05/tfs-2012-sharepoint-2013-integration-series-tfs-2012-sharepoint-2013-%e6%95%b4%e5%90%88-%e5%89%8d%e8%a8%80/'
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - Sharepoint 2013
  - SQL Server 2012
  - TFS2012
---
在2012年時上過一些 有關 **Application LifeCycle Management**的 **seminar**  
令到我對設定個良好的**開發架構**十分大興趣  
**Visual Studio 2012**, **TFS 2012**, **SQL 2012** 和 **SharePoint 2013**也都推出了一段日子了  
所以我都希望可以在公司上建設一個有系統的開發架構  
E.G.  
好好運用**TFS** 有的功能  
例如  
使用TFS的  
**Source Control**

  * <span style="line-height: 1.714285714; font-size: 1rem;">&#8211; 設定一些<strong>Check-in</strong>的<strong>Rule</strong> 去確保大家的Code 是符合 <strong>Coding Standard E.G. Follow StyleCop </strong>的Rules</span>
  * <span style="line-height: 1.714285714; font-size: 1rem;">&#8211; 利用<strong>Code Review</strong> 和待其他<strong>Developer</strong>審查你的程式碼 這可<strong>以提昇大家的Coding 技巧和Logic</strong></span>
  * <span style="line-height: 1.714285714; font-size: 1rem;">&#8211; <strong>Test Service</strong> Developer可以寫一些Unit Test去確保將來寫的Code 不會影響之前寫的Code的結果</span>
  * <span style="line-height: 1.714285714; font-size: 1rem;">&#8211; 當使用者<strong>Check-i</strong>n Code之後Test Service便會執行Test Case去看看有沒有Test Case Fail如果有的話..要解決了才可以成功<strong>Check-in</strong></span>
  * <span style="line-height: 1.714285714; font-size: 1rem;">&#8211;<strong> Build Service</strong> 這可以確保即使Check-in 的程式碼可以Pass <strong>Test Case</strong>之後..亦都可以成功地Build這些程式碼 , 有很多時候Developer都會說&#8230;他們的程式碼是可以執行的..沒有問題..<br /> 但是每每都是在Server上或客戶端上..出現問題..<br /> 我們建立了<strong>Build Server</strong>之後便可以確保程式碼不只是在Developer的機器上才可以執行了<br /> 這亦都可以加入一點設定令到Check-in 了的程式碼可以自行Deploy到 要執行的Server上&#8230; ETC</span>

和**SharePoint整合**了之後..  
可以在**Report Section** 上給管理人員看**Project**的進度  
亦都可以使用**Sharepoint**的**Portal** 放和**Project**有關的文件  
和很多很多有用的功能&#8230;

所以很想很想快快的在公司建立這一個架構..  
做了很多research之後..  
找了一些教學  
發現很多的教學都不是和公司開發環境有關的..  
多數都是一些**Proof of concep**t的教學&#8230;  
都是在自己的VM 內..沒有和**Domain**/**實戰相關**的&#8230;  
最後我還是忍不住..嘗試follow這些教學..  
到最後成功設定了 **TFS**.. 和安裝了**SharePoint**..  
很可惜在建立新的**Project**時不能自動建立Project Portal..  
否則會出現一個**User Not Found**的問題  
&#8220;<span style="color: #ff0000;"><strong>TFS218017 The User does not exist or is not unique</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2652" alt="TFS218017 The User does not exist or is not unique" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/BAPW40PCAAA39ZW.jpg?resize=530%2C223" width="530" height="223" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/BAPW40PCAAA39ZW.jpg)

**解決方法:**  
需要自行建立**Project Portal** 後再建立**TFS** 的Project  
..由於這不太方便..亦都不是想逹到的效果..  
經過很長時間的research和嘗試不同的解決方法..  
最後都是放棄了..

到了最近又再嘗試自己慢慢研究怎樣安裝/設定  
**TFS2012 SharePoint 2013 Integration**

今天終於成功把**TFS 2012** 和 **SharePoint 2013**整合了  
[<img class="alignnone size-full wp-image-2653" alt="Sample TFS 2012 Web Access Portal" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SampleTFSPortal.jpg?resize=625%2C567" width="625" height="567" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SampleTFSPortal.jpg)

還有期待已久 **SharePoint TFS Project Portal &#8211; Project Dashboard**  
[<img class="alignnone size-full wp-image-2657" alt="SharePoint TFS Project Portal - Project Dashboard" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/Project-Dashboard-Google-Chrome.jpg?resize=625%2C358" width="625" height="358" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/Project-Dashboard-Google-Chrome.jpg)  
在將來的網誌我會和大家仔細分享在  
**TFS2012 SharePoint 2013 Integration**時安裝和設定要留意的東西

Hope you find it useful