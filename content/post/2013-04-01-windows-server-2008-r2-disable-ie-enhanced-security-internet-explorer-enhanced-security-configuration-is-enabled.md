---
id: 2669
title: 'Windows Server 2008 R2 disable IE Enhanced Security &#8211; Internet Explorer Enhanced Security Configuration is enabled'
date: 2013-04-01T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2669
permalink: /2013/04/windows-server-2008-r2-disable-ie-enhanced-security-internet-explorer-enhanced-security-configuration-is-enabled/
categories:
  - Windows Server
tags:
  - troubleshooting
---
今天終於有部**Virtual Machine**可以給我嘗試做  
<a title="TFS 2012 SharePoint 2013 Integration Series –  TFS 2012 SharePoint 2013 整合 前言" href="http://blog.sharechiwai.com/2013/05/tfs-2012-sharepoint-2013-integration-series-tfs-2012-sharepoint-2013-%e6%95%b4%e5%90%88-%e5%89%8d%e8%a8%80/" target="_blank"><strong>TFS2012 SharePoint 2013 Integration</strong></a>

有VM之後第一個Step當然是做一個**Windows Update**和 **Download** 要用的應用程式  
[**TFS 2012**, **SQL Server 2012** 和 **SharePoint 2013**]  
當開啟 **IE** 之後便出現了以下的資訊

&#8220;<span style="color: #ff0000;"><strong>Internet Explorer Enhanced Security Configuration is enabled</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2671" alt="Internet Explorer Enhanced Security Configuration is enabled" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Internet-Explorer-Enhanced-Security-Configuration-is-enabled.jpg?resize=625%2C237" width="625" height="237" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Internet-Explorer-Enhanced-Security-Configuration-is-enabled.jpg)

每當你登入任何一個網頁都會出現一個Pop-up叫你把這個網頁/網址加進安全網址列  
[<img class="alignnone size-full wp-image-2672" alt="IE Popup because Internet Explorer Enhanced Security Enabled" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/IEPopupFromESC.jpg?resize=625%2C391" width="625" height="391" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/IEPopupFromESC.jpg)

**解決方法1**:  
用另一部電腦下載另一個**browser**  
之後把安裝檔複製到這台Server上

**第二個方法**..  
亦都是我感到比較好的方法是  
在Server的設定上如果你是管理員的話**停用**這個 &#8220;**Internet Explorer Enhanced Security Configuration**&#8221;

**解決方法**:  
開啟 &#8220;**Server Manager**&#8221;  
之後按一下第一個Node&#8221;**Server Manager** [**你的Server 名稱**]&#8221;  
在右面便會出現和這台**Server**相關的**Server Summary**  
在&#8221;**Security Information**/**安全資訊**&#8221; section的右方 應該有一個 叫 &#8220;**Config IE ESC**&#8221; 的連結  
[<img class="alignnone size-full wp-image-2673" alt="Server Manager IE ESC" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/ServerManagerIEESC.jpg?resize=625%2C427" width="625" height="427" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/ServerManagerIEESC.jpg)  
按一下&#8221;**Config IE ESC**&#8221; 之後便會看到以下的這一個畫面  
&#8220;**Internet Explorer Enhance Security Configuration**&#8221;  
[<img class="alignnone size-full wp-image-2674" alt="IE Enhanced Security Configuration Settings" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/IEESCOffForAdmin.jpg?resize=436%2C456" width="436" height="456" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/IEESCOffForAdmin.jpg)

在這裡我會建議 在 &#8220;**Administrator**/**管理員**&#8221; 的權限上關掉 這個 **&#8220;IE ESC**&#8220;的設定  
但是在其他 Users上 還是把&#8221;**IE ESC**&#8220;的設定保持啟動  
按一下 &#8220;**OK**/**確定**&#8221; 便可以了

再次開啟網頁時已經不會再有這些Warning的 Popup了

Hope you find it useful

* 如果在Windows Server 2003 有相同的問題的話.. 可以參考以下網誌

<a title="Permalink to Windows Server 2003 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled" href="http://blog.sharechiwai.com/2013/04/windows-server-2003-disable-ie-enhanced-security-internet-explorer-enhanced-security-configuration-is-enabled/" rel="bookmark">Windows Server 2003 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled</a>