---
id: 2111
title: 'How to display HTML data on ASP.Net MVC 3 &#8211; 如何顯示把資料庫上的HTML 放進 asp.net mvc 3 上'
date: 2011-09-12T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2111
permalink: '/2011/09/how-to-display-html-data-on-asp-net-mvc-3-%e5%a6%82%e4%bd%95%e9%a1%af%e7%a4%ba%e6%8a%8a%e8%b3%87%e6%96%99%e5%ba%ab%e4%b8%8a%e7%9a%84html-%e6%94%be%e9%80%b2-asp-net-mvc-3-%e4%b8%8a/'
categories:
  - ASP.Net MVC
---
如何顯示把資料庫上的**HTML** 放進 **asp.net mvc 3** 上  
今天開始在公司的其中一個網頁上把之前從**Rich Text Editor**輸入的資料顯示出來  
我的做法是把資料庫的相關資料加進 **ViewBag**上.  
E.G.  
<span style="color: #008000;"><strong>ViewBag.Notice =<h1> Share ChiWai ASP.Net MVC3 Show HTML Sample</h1></strong></span>

# <span class="Apple-style-span" style="color: #333333; font-weight: 300;">我的 Controller</span>

[csharp]  
public ActionResult Index()  
{

ViewBag.Notice = "<h1> Share ChiWai ASP.Net MVC3 Show HTML Sample</h1>";  
ViewBag.NoticeNewHTMLString = new HtmlString("<h1> Share ChiWai ASP.Net MVC3 Show HTML Sample</h1>");  
return View();  
}

[/csharp]

之後發現出現了一個小問題..  
就是這個句子整句在網頁上顯示出來..  
而**HTML 的Markup 沒有被Render.**..  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3c9d2e4ba95e4f3aad2b415e3bcff88a/renditions/fullsize.jpg?resize=625%2C361" alt="" width="625" height="361" data-recalc-dims="1" /> 

我便在想..是不是我應該使用**HTML.Decode** 來解決這個問題..  
用**HTML.Decode**也沒有什麼效果  
也嘗試用 **new HtmlString**.. 結果也沒有分別  
最後終於找到解決方法了

**解決方法**:  
只要在**cshtml**中使用  
**html.raw**便可以了

或者是在 **Code Behind** 使用 **new HtmlString** 來轉換這個**HTML Markup**

以下是我的**cshtml**:

<pre>Original:
&lt;br /&gt;
@ViewBag.Notice
&lt;br /&gt;
New HTML String From Code Behind:
&lt;br /&gt;
@ViewBag.NoticeNewHTMLString
&lt;br /&gt;
New HTML String From cshtml:
&lt;br /&gt;
@{new HtmlString(ViewBag.Notice);}
&lt;p /&gt;

HTML Encode:
&lt;br /&gt;
@Html.Encode(ViewBag.Notice)
&lt;p /&gt;
Raw HTML:
&lt;br /&gt;</pre>

結果:  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8d623af1d9a847db8520bade913b2e2d/renditions/fullsize.jpg?resize=625%2C544" alt="" width="625" height="544" data-recalc-dims="1" /> 

Hope you find it useful