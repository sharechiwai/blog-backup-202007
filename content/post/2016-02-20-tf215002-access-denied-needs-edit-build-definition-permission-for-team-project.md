---
id: 3602
title: 'TF215002: Access denied. needs Edit build definition permission for team project'
date: 2016-02-20T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3602
permalink: /2016/02/tf215002-access-denied-needs-edit-build-definition-permission-for-team-project/
categories:
  - Visual Studio Online
tags:
  - Microsoft Azure
  - TFS
  - TFS Services
  - Visual Studio Online
  - Windows Azure
---
嘗試使用Azure Web App 中的**Set up deployment from source control** [**Visual Studio Online**/ **TFS Service**]  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1612/25033045992_d94f1cf78c_z.jpg?resize=482%2C143" alt="Azure - Set up deployment from source" width="482" height="143" data-recalc-dims="1" />  
誰不知當我嘗試連接 **Visual Studio Onlin**e的**Project**時出現了以下的錯誤信息  
&#8220;<span><strong><span style="color: #ff0000;">TF215002: Access denied. needs Edit build definition permission for team project</span></strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1508/25058038061_d63ab2f4f1_z.jpg?resize=625%2C83" alt="TF215002: Access denied. needs Edit build definition permission for team project" width="625" height="83" data-recalc-dims="1" />  
[我的**Azure Account** 的Email 不是我用來建立 **Visual Studio Online的 account**..所以便有這個問題出現]

花了很多時間在做research 但是可惜都是找不到怎樣可以 **Assign Permission** 給**Azure**的 **Visual Studio Online**的使用者  
有&#8221;**Edit build definaion permission for team project**&#8221; 的權限  
經過很久的嘗試..終於找到解決方法

**解決方法**  
我們可以先登入 建立這個 **Visual Studio** 的**repository** 的使用者  
之後選擇這個將會發報到 **Azure的 Project** 的**repository** 上  
在網頁的右上方 按一下 &#8220;**Manage Project**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1460/24520627454_d35a3d011d_z.jpg?resize=507%2C245" alt="Visual Studio Online - Manage Project" width="507" height="245" data-recalc-dims="1" />  
之後選擇&#8221;**Security** &#8220;分頁  
按一下&#8221;**Build Administrators**&#8221;  
之後按一下&#8221;**Members**&#8221;  
按一下 &#8220;**Add**&#8221;  
去加入有**Azure Account**的那個**Visual Studio Online的使用者**  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1680/25058038161_a961f6034b_z.jpg?resize=625%2C233" alt="Visual Studio Online Project Settings - Security - Build Administrators" width="625" height="233" data-recalc-dims="1" />  
之後再次回到**Azure** 嘗試**Set up deployment from source control**  
應該便會成功了  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1515/24855644210_9a407e63b1_z.jpg?resize=625%2C73" alt="Visual Studio Online Project is linked to the Windows Azure Web app" width="625" height="73" data-recalc-dims="1" />  
Hope you find it useful