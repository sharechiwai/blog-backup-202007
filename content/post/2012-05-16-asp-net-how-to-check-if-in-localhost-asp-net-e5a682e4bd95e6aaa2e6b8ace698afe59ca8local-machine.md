---
id: 2485
title: 'ASP.Net How to check if in localhost &#8211; ASP.Net 如何檢測是在Local Machine?'
date: 2012-05-16T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2485
permalink: '/2012/05/asp-net-how-to-check-if-in-localhost-asp-net-%e5%a6%82%e4%bd%95%e6%aa%a2%e6%b8%ac%e6%98%af%e5%9c%a8local-machine/'
categories:
  - ASP.Net MVC
---
今天開始為**ASP.Net MVC**的Project加入一些 **Logging**的功能&#8230;  
這些功能會把一些**Transaction** 記錄到**Database**上  
或者把**Application Error Email** 給負責的同事..  
由於這個Project還是在開發中  
所以不希望會把所有在開發時的Transaction和出現的Error 也發Email

**解決方法很簡單**..  
第一個方法是在**Web.Config** 檔案上設定一個變數&#8230;  
來決定會不會把記錄記下和發電郵..  
另一個方法是使用程式碼來判斷目前的網址是不是**Local**  
不是的話才記錄資料和發Email

**判斷是不是Local的程式碼**是:

**CSharp**

[csharp]  
bool isLocal = HttpContext.Current.Request.IsLocal;  
if(!isLocal){  
//記錄資料1  
}  
[/csharp]

Hope you find it useful