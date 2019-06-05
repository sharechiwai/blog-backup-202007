---
id: 2664
title: '&#8220;Windows cannot find &#8216;E:\prerequisteninstaller.exe&#8217; Make sure you typed the name correctly, and then try again&#8221;'
date: 2013-04-03T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2664
permalink: /2013/04/windows-cannot-find-eprerequisteninstaller-exe-make-sure-you-typed-the-name-correctly-and-then-try-again/
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Sharepoint 2013
  - troubleshooting
  - Windows Server
---
在安裝完了**SharePoint Server 2013**的 **Preparation Tools**之後  
電腦需要重新啟動..  
電腦重新啟動後便出現了以下的錯誤信息&#8230;  
這應該是因為我是和**ISO** 來安裝**SharePoint 2013**而不是用**DVD** 來安裝的關係..  
當電腦啟動後因為在**Virtual DVD Rom Load**起 **SharePoint 2013**的 **ISO**之前  
已執行了這一個執行&#8221;**E:\prerequisteninstaller.exe**&#8221; 的**程式碼/script**..  
所以即使在&#8221;**Computer**/**電腦**&#8220;上看到這一個檔案..他也投訴找不到檔案

每當**Server**重新啟動..他都會彈出這個錯誤信息..  
&#8220;<span style="color: #ff0000;"><strong>Windows cannot find &#8216;E:\prerequisteninstaller.exe&#8217; Make sure you typed the name correctly, and then try again</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2676" alt="Windows Server 2008R2  SharePoint Preparation Tools Complaint File not found when computer start up" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Server2008R2_SharePointComplainCantFindexe.jpg?resize=625%2C314" width="625" height="314" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Server2008R2_SharePointComplainCantFindexe.jpg)

**解決放法**十分簡單:  
這個情況的發生  
應該是在安裝**SharePoint Preparation Tools** 時..他有些程式碼把一個**Bat** 檔案加入了  
&#8220;**Start Up**/**啟動**&#8221; 的資料夾..  
所以每當**Server**重新啟動 都會執行這個程式碼&#8230;

大家只要按一下&#8221;**開始**/**Start**&#8221; ->&#8221;**所有程式集**/**All Programs**&#8221;  
之後開啟 &#8220;**Start Up**/**啟動**&#8220;資料夾 **把和這個行動有關的 bat 檔案/程式刪除**便可以了  
[<img class="alignnone size-full wp-image-2677" alt="SharePoint Server Preparation Tool Startup Script Location" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SharePointServerPreparationToolStartupScript.jpg?resize=405%2C527" width="405" height="527" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SharePointServerPreparationToolStartupScript.jpg)

Hope you find it useful