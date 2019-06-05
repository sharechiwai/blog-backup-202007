---
id: 2609
title: 'Sharepoint server Log path /  Sharepoint 的記錄在那裡'
date: 2012-11-25T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2609
permalink: '/2012/11/sharepoint-server-log-path-sharepoint-%e7%9a%84%e8%a8%98%e9%8c%84%e5%9c%a8%e9%82%a3%e8%a3%a1/'
categories:
  - Sharepoint
tags:
  - TFS 2012 With Sharepoint 2013 Integration
---
最近開始嘗試在公司的Development Server上  
設定**TFS 2012 With Sharepoint 2013 Integration**.  
不知道為什麼..常常出現 **Sharepoint permission**的問題

所以便要嘗試去看看**Sharepoint Server** 上的 Log了  
但是不知道應該從那裡入手..

做了一會資料research 之後終於找到了Sharepoint server Log path了

**解決方法**

大家可以在資料來上的網址列輸入

&#8220;**%commonprogramfiles%/Microsoft Shared/web server extensions/<span style="color: #ff0000;">[XX Version]</span>/Logs**&#8221;  
把[XX Version] replace到你所用的Sharepoint 版本便可以了  
E.g. 我使用的是**Sharepoint 2013**  
所以我的路徑會是  
&#8220;**%commonprogramfiles%/Microsoft Shared/web server extensions/<span style="color: #ff0000;">15</span>/Logs**&#8221;

Hope you find it useful