---
id: 2928
title: 'TFS2012 / TFS Delete Team Project &#8211; 在TFS 2012 / TFS 如何刪除 Team Project'
date: 2013-10-02T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2928
permalink: '/2013/10/tfs2012-tfs-delete-team-project-%e5%9c%a8tfs-2012-tfs-%e5%a6%82%e4%bd%95%e5%88%aa%e9%99%a4-team-project/'
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - TFS
---
今天差不多完成測試**TFS2012 SharePoint 2013 Integration**  
成功把之前的**Reporting Service** 解決了  
將來有時間再和大家分享解決的方法

現在嘗試清理一下 **TFS Server** 上之前建立用來測試  
**TFS 2012 SharePoint 2013 Integration** 的**Sample Project**  
和之前在TFS 上建立的**Potential Projects** 太久沒有真的開始開發&#8230;  
所以都可以清理他們

**解決方法**:  
我們可以用**Visual Studio**的**Command Prompt**  
E.g. **Start** /開始-> **All Programs/所有程式集** -> **Visual Studio 2012 -> Visual Studio Tools** &#8220;**Developer Command Prompt for VS**&#8221;  
[<img class="alignnone size-full wp-image-2935" alt="VS2012 Developer Command Prompt" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/VS2012DeveloperCMD.jpg?resize=529%2C257" width="529" height="257" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/VS2012DeveloperCMD.jpg)

[<img alt="Visual Studio 2012 - Developer Command Prompt for VS2012" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/VS2012DeveloperCmd.png?resize=423%2C224" width="423" height="224" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/VS2012DeveloperCmd.png)

在**Command Prompt** 上我們可以使用**TFSDeleteProject** 這個指令來刪除 **TFS Server**上的 **Team Project.**  
這個指令是這樣的

<span style="color: #339966;"><strong>> TFSDeleteProject /collection:[TFS Collection 的 URL] &#8220;[TFS Project 的名稱]&#8221;</strong></span>

**E.g.**  
假設你的**TFS Server**的 網址是 **http://tfs02:8080**  
要刪除的 **Team Project**是 **TFS2012Sample**  
**Collection** 名是**SampleCollection**  
那你的網址便會像這一個  
**http://tfs02:8080/SampleCollection**

那你便要在**Command Prompt** 輸入以下指令  
**<span style="color: #339966;">> TFSDeleteProject /collection:http://tfs02:8080/SampleCollection &#8220;TFS2012Sample&#8221;</span>**  
之後按**Enter**/**輸入  
[<img class="alignnone size-full wp-image-2929" alt="Developer Command Prompt for VS2012 Delete Team Project" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Developer-Command-Prompt-for-VS2012_DeleteTeamProject.jpg?resize=625%2C125" width="625" height="125" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Developer-Command-Prompt-for-VS2012_DeleteTeamProject.jpg)  
** 

之後他便彈出一些警告信息說明刪除 **TFS Project**會有什麼影響  
**E.G.**  
刪除 **TFS Project**之後是不可以還原的  
所有**Version Control**, **Work Item**, **Build Data**都會被刪除..  
如果想還原的話.你便需要還原**TFS** 的資料庫

輸入 &#8220;**Y**&#8220;確定刪除 **TFS Project** 否則 輸入&#8221;**N**&#8221;  
[<img class="alignnone size-full wp-image-2930" alt="TFSDeleteProject Confirm" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectConfirm.jpg?resize=625%2C146" width="625" height="146" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectConfirm.jpg)

輸入&#8221;**Y**&#8221; 之後 如果你的 TFS 是有整合**SharePoint**的話 他便會彈出一些警告信息

[<img class="alignnone size-full wp-image-2931" alt="TFSDeleteProject Confirm Delete SharePoint Portal" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectConfirmDeleteSharePoint.jpg?resize=625%2C181" width="625" height="181" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectConfirmDeleteSharePoint.jpg)  
問你想不想刪除和這個**Team Project**相關的 **SharePoint Website** 如果這個**Project的SharePoint** **Website**是和其他Project共用的話&#8230;其他**Project**便不能用這個**SharePoint site**了

在我的情況下我是做了 **TFS 2012 SharePoint 2013 Integration**的..所以我是有**Project Web Portal** / **SharePoint Website** 的

因為我知道我沒有共用 **SharePoint Site**  
我選擇輸入&#8221;**Y**&#8220;, 之後便開始刪除 **TFS Project** 相關的東西了  
[<img class="alignnone size-full wp-image-2932" alt="TFSDeleteProject Deleting" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProject_Deleting.jpg?resize=625%2C356" width="625" height="356" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProject_Deleting.jpg)

很快便完成了  
[<img class="alignnone size-full wp-image-2933" alt="TFSDeleteProject Completed" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectCompleted.jpg?resize=625%2C487" width="625" height="487" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/TFSDeleteProjectCompleted.jpg)

Hope you find it useful