---
id: 3388
title: ASP.Net MVC 5 Membership.GetUser() Issue
date: 2015-02-22T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3388
permalink: /2015/02/asp-net-mvc-5-membership-getuser-issue/
categories:
  - ASP.Net MVC
tags:
  - ASP.Net Troubleshooting
---
今天公司發佈了新的網站

由于沒有好好的做**QA** / **測試**..  
所以今天發現了很多的問題&#8230;  
[如果他們一早聽我之前建議的做法..應該不用那麼失策的]

今天的其中一個問題是和 **Asp.Net Membership** 和 **Asp.Net Identity**有關的  
自從**Asp.Net MVC 5**開始 **Asp.net**的 **Membership** 便用了 **ASP.Net Identity** 來取代  
之前的 **ASP.NET Membership** 和 **Simple Membership systems**  
**ASP.NET Membership** 和 **Simple Membership systems**便不能在**ASP.Net MVC 5**的網站上使用  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8578/16651459835_bb5defb711_z.jpg?resize=625%2C173" alt="ASP.Net Identity vs ASP.Net Membership system" width="625" height="173" data-recalc-dims="1" /> 

所以公司的其中一位同事便將公司另一個網站的**asp.net mvc3**轉乘**mvc5**在他的電腦上測試是完全沒有問題的  
當我們要把所有系統更新的時候把網站發放到伺服器上變出現了一個登入的問題在登入期間需要花一分半鐘才能進入主頁  
公司的其中一個網絡顧問說是我們程式碼的問題..

但是我的同事卻說在他電腦上運行沒有問題  
所以應該是網絡的問題  
[作一些沒有意思的Argue]  
最後因為覺得沒有意思浪費時間說誰對誰錯  
所以我變進行了一個小小的除錯個步驟  
發現應該是這個程式碼的問題

之後發現原來同事升級網頁的時候真的直接把**Asp.Net MVC3** 升級到 **Asp.Net MVC5**  
但是沒有把所有和membership有相關的程式碼轉換成使用**identity**  
所以當我在除錯模式是執行這個網頁是在**membership**這個功能花了很久才能執行下一段程式碼  
解決方法十分簡單我們只需要把所有和**membership**相關的程式碼轉換成identity便可

**解決方法**  
我們只需要把之前使用的 **Membership.GetUser**()  
轉成 **User.Identity** 便可以了

**E.G.**  
<pre>  
string Username = Membership.GetUser().UserName;  
</pre>  
**轉成**  
<pre>  
string Username = HttpContext.Current.User.Identity.GetUserName();  
</pre>

Hope you find it useful