---
id: 2459
title: 'ASP.Net/ ASP.Net MVC Get Client IP Address &#8211; 在ASP.Net /ASP.Net MVC上 如何取得用戶的IP Address'
date: 2012-05-08T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2459
permalink: '/2012/05/asp-net-asp-net-mvc-get-client-ip-address-%e5%9c%a8asp-net-asp-net-mvc%e4%b8%8a-%e5%a6%82%e4%bd%95%e5%8f%96%e5%be%97%e7%94%a8%e6%88%b6%e7%9a%84ip-address/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net VS ASP.Net MVC3
  - ASP.Net Web Application To ASP.Net MVC 新手筆記
---
今天開始為公司的**ASP.Net MVC** 網站加設一些保安用的記錄 **Security Logging**的功能&#8230;  
主要是當客戶查詢時在那些時間他的戶口有人登入過&#8230;etc  
方法十分簡單  
只要建立一個Database Table  
把登入/登出的時間和I**P Address**記下來便可以了&#8230;

之後我們便要在**ASP.Net**/**ASP.Net MVC**上取後我們用戶的**IP Address**了

**方法十分簡單**  
只是在**ASP.Net**的Code Behind 上  
或在**ASP.Net MVC** 的 Controller 上 便用以下的程式碼  
便可以取得用戶的IP Address了

[csharp]  
string IP = Request.Params["REMOTE_ADDR"].ToString();  
//或  
string UserHostName = Request.UserHostName;  
//或  
string UserHostAddress = Request.UserHostAddress;  
[/csharp]

如果你想在Class 上面取得用戶的IP Address的話  
可以嘗試以下方法

[csharp]  
string IP = System.Web.HttpContext.Current.Request.UserHostAddress;  
[/csharp]

如果有更好的方法, 請留言給我  
謝謝

Hope you find it useful