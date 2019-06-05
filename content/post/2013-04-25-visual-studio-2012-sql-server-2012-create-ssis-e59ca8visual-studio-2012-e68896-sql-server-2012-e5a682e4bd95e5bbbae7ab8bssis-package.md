---
id: 2795
title: 'Visual Studio 2012 / SQL Server 2012 create SSIS &#8211; 在Visual Studio 2012 或 SQL Server 2012 如何建立SSIS Package?'
date: 2013-04-25T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2795
permalink: '/2013/04/visual-studio-2012-sql-server-2012-create-ssis-%e5%9c%a8visual-studio-2012-%e6%88%96-sql-server-2012-%e5%a6%82%e4%bd%95%e5%bb%ba%e7%ab%8bssis-package/'
categories:
  - SSIS
tags:
  - SQL Server Business Intelligence Development Studio
  - SQL Server Data Tools
  - VS2012
---
今天嘗試在新安裝的電腦上建立一個**SQL Server Integration Service**的 專案..來做一個**Import CSV**的工作..[主要是用來寫一個功能..可以令到將來可以執行來**Import**和更新資料]

在**SQL Server 2008**的時候..  
我們可以開啟 **Microsoft SQL Server 2008** 中的 &#8220;**SQL Server Business Intelligence Development Studio**&#8221; 來建立**SSIS** 的 **Package**&#8230;  
[<img class="alignnone size-full wp-image-2799" alt="SQL Server Business Intelligence Development Studio - Visual Studio 2008" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerBusinessIntelligenceDevelopmentStudio.png?resize=361%2C258" width="361" height="258" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerBusinessIntelligenceDevelopmentStudio.png)  
誰不知..在我的**Windows 8** + **Visual Studio 2012** 和 **SQL Server 2012**中卻找不到  
[<img alt="SQL Server Project in Visual Studio 2012" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerProject.png?resize=625%2C511" width="625" height="511" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerProject.png)

而**Visual Studio 2012** 中只有&#8221;**SQL Server Database Project**&#8221;

試了一段時間後終於找到解決方法了

**解決方法**:  
原來在**SQL Server 2012**中的 &#8220;**SQL Server Business Intelligence Development Studio**&#8221; 程式改了名稱為 &#8220;**SQL Server Data Tools**&#8221;  
[<img class="alignnone size-full wp-image-2797" alt="SQL Server Data Tools in Windows 8" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerDataTools.png?resize=490%2C359" width="490" height="359" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQLServerDataTools.png)

開啟了 &#8220;**SQL Server Data Tools**&#8220;後便看到了 似曾相識的 **Project Template** 了  
&#8220;**Business Intelligence**&#8221; -> &#8220;**Integration Services**&#8221;  
[<img class="alignnone size-full wp-image-2796" alt="SSIS In Visual Studio 2010" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SSISInVS2010.png?resize=625%2C489" width="625" height="489" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SSISInVS2010.png)  
&#8220;**Integration Services Project**&#8221;

終於可以開始開發我的**SSIS Package**了

Happy Coding