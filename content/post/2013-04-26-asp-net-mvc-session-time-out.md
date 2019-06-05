---
id: 2805
title: ASP.net MVC Session Time out
date: 2013-04-26T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2805
permalink: /2013/04/asp-net-mvc-session-time-out/
categories:
  - ASP.Net MVC
---
在寫**ASP.Net MVC** 的程式時..常常發現 很快便會**Session time out**  
很多時候在開發過程中.. 都可能要**Debug**..更**改Stored procedure** 或其他的東西..  
很多時候都可能沒有按過頁面的連結超過**20分鐘**.. 過了二十多分鐘得再按下連結時..  
便會出現登出發沒有顯示資料等等的情況..

這時候很大機會是**Session timeout**所導致的..

**解決方法**十分簡單..  
只要在開發模式中的<span style="color: #3366ff;"><strong>Web.config</strong></span> 修改一下 **Session State timeout**的時間便可以了  
**E.G.**

在**Web.config** 的 **System.web**分支下 加入 或修改 &#8220;**sessionState timeout**&#8221; 的屬性 便可以了

[xml]  
<system.web>  
<sessionState timeout="60" />  
</system.web>  
[/xml]

Hope you find it useful