---
id: 2870
title: TFS 2012 SharePoint 2013 Integration / TFS2012 Migration Notes
date: 2013-05-15T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2870
permalink: /2013/05/tfs-2012-sharepoint-2013-integration-tfs2012-migration-notes/
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - Sharepoint 2013
  - SQL Server 2012
  - TFS
---
今天終於完成了 **TFS 2012 SharePoint 2013 Integration  
[<img class="alignnone size-full wp-image-2871" alt="TFS 2012 SharePoint 2013 Integration" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/1270584_10151871116071399_1968886502_o.jpg?resize=625%2C362" width="625" height="362" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/1270584_10151871116071399_1968886502_o.jpg)**  
由於自己的寫作/組織能力不太好..  
需要一些時間去整理筆記 才可以和大家分享我的  
**TFS 2012 SharePoint 2013 Integration** 的經驗  
在寫**TFS 2012 SharePoint 2013 Integration** 的 **note**之前我會先上載  
我的試驗環境是這樣的  
**Hardware/ 硬件**  
是一個以 **VMWare VSphere 5** 做的 **Virtual Environment**  
主機是一個很強的**Dell Server**  
這部Virtual Server [**TFS02**] 得到的資源有  
**100GB** 的 **C drive for System/Install** 檔  
好像是**100GB** 的　**D Drive for data**  
現在是用**10GB RAM** 如果不足夠再加  
**4 CPU 2.39 GHz**的 [model 不太清楚]

**Software**  
**Windows Server 2012**  
**SQL Server 2012** [安裝了 Database Engine, Analysis Service, Reporting Service]  
**Team Foundation Server 2012**  
**SharePoint Server 2013**

大概是這樣吧&#8230;

我的任務是把公司現有的**TFS 2010 升級到 TFS2012**  
現有的**TFS 2010**我們只用了他的**Source Control** 功能  
沒有使用他的**Reporting** / 或好好運用他的**Work Item** / **Bugs**/ **Issue**/ **Task** 等等的 東西 用來做**Project Tracking**  
和 **Build Service**/ **Test Server**等等的好東西 來令到開發更有效率  
所以今次升級 **TFS2010** 到 **TFS 2012** 希望可以盡量使用 **Team Foundation Server** 所提供的功能  
E.G **Reporting**&#8230;  
配合 **SharePoint Integration** 希望能夠給 其他不是 **Developer**的同事一個 好好的 **Web Portal** 令到大家更加了解這個Project  
以減少常常重複要回答Email 的問題..  
希望使用**SharePoint** 做一個 **Document Repository** 用來給他們一個地方 看看開發進度和找其他有用的資訊&#8230;  
Please correct me if my concept is wrong..

由於寫作能力有限..所以我會先寫一些我在安裝/設定**TFS 2012 SharePoint 2013 Integration**時遇到的問題  
將來有時間才把所有的步驟仔細的寫下來&#8230;

如果有問題的話..歡迎大家留言給我

Hope you find it useful.