---
id: 3661
title: 'Remove Reponse Header on ASP.Net MVC &#8211; 移除 ASP.Net MVC 的響應頭'
date: 2016-05-12T00:00:30+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3661
permalink: '/2016/05/remove-reponse-header-on-asp-net-mvc-%e7%a7%bb%e9%99%a4-asp-net-mvc-%e7%9a%84%e9%9f%bf%e6%87%89%e9%a0%ad/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net
  - ASP.Net MVC
  - Security
---
最近公司終於分配了一些比較有趣的任務給我  
可以明正言順地在公司做Research  
之後測試  
這個任務就是增強公司的那個**ASP.Net MVC 網站的保安**  
以免被人入侵

最了一些research之後 發現有很多東西可以做 以減少被入侵的風險  
今天想介紹給大家的是把 如何把MVC 的 **Server Response Header 移除**

原因  
當有某一些安全漏洞被發現時  
E.G. 針前某一些web server或 programming language  
如果你的 web site的 **Reponse Header**把你的**Server Config**都 Response出來的話  
那麼入侵者便可以得容易知道你的網站可以是下一個目標

E.G.

Default的**ASP.Net MVC Website** 的 **Response Header會把 Web Server的 資料**  
E.G. **IIS 是什麼 Version**  
**用那一個.Net Framework和那一個 ASP.Net Version 都沒有保留地 response出來  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7116/26756682192_92c4466e63_z.jpg?resize=571%2C282" alt="Google Chrome Console website response header" width="571" height="282" data-recalc-dims="1" />  
** 

**解決方法**:

在 <span style="color: #0000ff;"><strong>Global.asax</strong> </span>上 加入以下的 程式碼

<pre>protected void Application_PreSendRequestHeaders()
        {
            Response.Headers.Remove("Server");
            Response.Headers.Remove("X-AspNet-Version");
            Response.Headers.Remove("X-AspNetMvc-Version");
            Response.Headers.Remove("X-Powered-By");
         
        }
        
</pre>

Hope you find it useful