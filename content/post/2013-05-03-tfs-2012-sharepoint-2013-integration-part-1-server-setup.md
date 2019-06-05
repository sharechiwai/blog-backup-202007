---
id: 2661
title: 'TFS 2012 SharePoint 2013 Integration &#8211; Part 1 Server Setup'
date: 2013-05-03T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2661
permalink: /2013/05/tfs-2012-sharepoint-2013-integration-part-1-server-setup/
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - SQL Server 2012
  - troubleshooting
  - Windows Server
---
由於在公司上我沒有權限可以直接接觸到**Virtual Server**/ **Virtual Machine** 安裝和設定的關係..  
如果自己在自己的電腦上建**Hyper-V** 再建立**Domain**/ **AD** 等等..太多東西要學..和要太多資源&#8230;要用再多的時間&#8230;所以不太可行

所以我只可以向上司Request 我需要的Virtual Machine大概有什麼..  
(最理想的是 **Windows Server 2012**, **8-12 GB Ram**, **80GB hard drive space**, 一個比較好的CPU)  
他們會安裝好 **OS** 和提供**Virtual Hardware** E.G. **CPU**, **RAM** 和**Hard Drive Space**  
經過了多個月(4個多用的申請)我的上司終於給了我一個**Virtual Machine** 可以用來嘗試  
**TFS SharePoint Integration**了  
誰不知..這個**Virtual Machine**跟我Request 的不太一樣  
系統是**Windows Server 2008 R2 6GB Ram** 和 不太強的**CPU**.. 還有**60GB** 的 **Hard Drive Space  
[<img class="alignnone size-full wp-image-2684" alt="Windows Server 2008 R2 - Server Information" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/ServerInfo.jpg?resize=625%2C295" width="625" height="295" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/ServerInfo.jpg)  
** 

雖然是慢一些..但是都可以用來嘗試能不能實現  
**TFS 2012 SharePoint 2013 Integration**

**在開始之前**.. 當然是要做一些準備的功夫..  
就是要確保 **Server**已經安裝了最新的更新 [執行**Windows Update**]  
如果大家是使用VM 的話&#8230;我會建議大家完成**Windows Update**  
之後做一個**Snapshot**&#8230;

**Windows Update**完成後便可以去**Download** 需要的軟件了  
如:[**TFS 2012**, **SQL Server 2012** 和 **SharePoint 2013]**

誰不知當我 **Launch IE** 的時候&#8230;  
他出現了  
&#8220;**Internet Explorer Enhanced Security Configuration is enabled**&#8221;  
當我輸入網址後便有一些**Pop Up Box** 彈出來叫我把這個網頁/網址加進安全網址列  
如果大家有相同的問題的話..  
可以參考以下的網誌.. 有解決 **IE ESC Enabled**的方法

**<a title="Permalink to Windows Server 2008 R2 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled" href="http://blog.sharechiwai.com/2013/04/windows-server-2008-r2-disable-ie-enhanced-security-internet-explorer-enhanced-security-configuration-is-enabled/" rel="bookmark">Windows Server 2008 R2 disable IE Enhanced Security – Internet Explorer Enhanced Security Configuration is enabled</a>**

解決完之後我便下載了**Microsoft SQL Server 2012**了

待續&#8230;