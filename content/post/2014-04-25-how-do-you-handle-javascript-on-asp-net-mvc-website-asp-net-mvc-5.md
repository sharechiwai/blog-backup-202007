---
id: 3152
title: 'How do you handle Javascript on ASP.Net MVC Website &#8211; ASP.Net MVC 5'
date: 2014-04-25T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3152
permalink: /2014/04/how-do-you-handle-javascript-on-asp-net-mvc-website-asp-net-mvc-5/
categories:
  - ASP.Net MVC
---
最近開始再次學習**ASP.Net MVC 5**  
科技推出得太快..很多東西都想學..  
所以常常都被不同的東西分了心

開始寫**ASP.Net MVC 5**的時候..嘗試做**cshtml**上使用**JQuery**做一些東西  
我的程式碼如下:  
**HTML**

[html]  
<h2 id="header">Javascript Section Demo &#8211; Failed</h2>

<div id="result">  
Original Div Content  
<p>  
Wait for Javascript to Load  
<p>  
</div>  
[/html]

**Javascript**

[javascript]  
<script>  
$(document).ready(function () {  
$("#result").html("Javascript Excuted");  
$("#header").html("Javascript Section Demo &#8211; Success");  
});  
</script>  
[/javascript]

誰不知..當我執行時出現了以下的錯誤..  
&#8220;<span style="color: #ff0000;"><strong>Uncaught ReferenceError: $ is not defined</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7304/14152577363_0822d2304f_z.jpg?resize=625%2C252" alt="ASP.Net MVC - Uncaught ReferenceError: $ is not defined" width="625" height="252" data-recalc-dims="1" /> 

**Failed Demo:**  
<a title="ASP.Net MVC - Javascript Section Demo - Failed" href="http://sharechiwaimvccloud.apphb.com/JsDemo/MvcJsScriptInitSample" target="_blank">http://sharechiwaimvccloud.apphb.com/JsDemo/MvcJsScriptInitSample<br /> </a>  
在想為什麼他認不了**JQuery**的呢?  
原來**ASP.Net MVC** 新增了一個 **Section** 叫**Scripts**的Tag  
這個可以增加網頁的效能..  
通常寫網頁的都建議把所有和**Rendering**沒有關係的程式碼都放在網頁的底部..  
這可以令到網頁顯然得更快

**解決方法**  
我們只要加所有和**Javascript** 相關係程式碼放進這個  
<span style="color: #008000;"><strong>Section scripts</strong> </span>**tag** 內便可以了  
E.G.

[csharp]

@section Scripts  
{  
<script>  
$(document).ready(function () {  
$("#result").html("Javascript Excuted");  
$("#header").html("Javascript Section Demo &#8211; Success");  
});  
</script>  
}

[/csharp]

<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2901/14132510765_20ec159814_z.jpg?resize=625%2C249" alt="Javascript working on ASP.Net MVC" width="625" height="249" data-recalc-dims="1" /> 

Working Demo:  
<a title="ASP.Net MVC - Javascript Section Demo - Success" href="http://sharechiwaimvccloud.apphb.com/JsDemo/MvcJsScriptInitSample?isSuccess=true" target="_blank">http://sharechiwaimvccloud.apphb.com/JsDemo/MvcJsScriptInitSample?isSuccess=true</a>

Hope you find it useful