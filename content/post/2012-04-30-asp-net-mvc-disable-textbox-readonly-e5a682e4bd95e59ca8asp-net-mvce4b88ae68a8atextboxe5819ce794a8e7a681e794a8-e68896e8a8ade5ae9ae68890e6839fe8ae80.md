---
id: 2405
title: 'ASP.Net MVC Disable TextBox/ ReadOnly &#8211; 如何在ASP.Net MVC上把TextBox停用/禁用 /或設定成惟讀'
date: 2012-04-30T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2405
permalink: '/2012/04/asp-net-mvc-disable-textbox-readonly-%e5%a6%82%e4%bd%95%e5%9c%a8asp-net-mvc%e4%b8%8a%e6%8a%8atextbox%e5%81%9c%e7%94%a8%e7%a6%81%e7%94%a8-%e6%88%96%e8%a8%ad%e5%ae%9a%e6%88%90%e6%83%9f%e8%ae%80/'
categories:
  - ASP.Net MVC
---
今天需要建立一個**Form**  
給使用者更新資料&#8230;  
有一些資料是不可以更變的..  
之前想用&#8221;Html.Label來解決的..  
可惜當把資料**Post**到**Controller**時**Value**卻變了**null**  
原因是因為我們需要用一些**Input Control** 來輪入資料吧  
所以便要使用 **TextBox**了 而要把禁止使用者更變這個TextBox的值  
我們可以設定**htmlAttributes** 把**Disabled**設定為true便可以了  
**解決方法**:  
**@Html.TextBox(&#8220;HTML Control的名&#8221;,&#8221;這個TextBox的值&#8221;, HTML 特性設定/htmlAttributes new{ disabled=&#8221;true&#8221;})**

E.G.

[csharp]  
@Html.TextBox("PhoneNumber",Model.PhoneNumber, new{ disabled="true"})  
[/csharp]

很可惜&#8230;問題還是沒有解決&#8230;都是把資料變成了**null**  
最後終於找到解決方法了  
我是需要把**TextBox**變成**ReadOnly**便可

[csharp]  
@Html.TextBox("PhoneNumber",Model.PhoneNumber, new{ @readonly="true"})  
[/csharp]

***<span style="color: #ff0000;">請注意我們需要在readonly之前加上 &#8220;@&#8221; 的</span>**  
** <span style="color: #ff0000;">E.G. @readonly</span>**  
** <span style="color: #ff0000;">因為readonly是一個reserve word</span>**

Hope you find it useful