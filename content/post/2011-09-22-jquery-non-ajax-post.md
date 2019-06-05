---
id: 2099
title: JQuery Non-Ajax Post
date: 2011-09-22T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2099
permalink: /2011/09/jquery-non-ajax-post/
categories:
  - ASP.Net MVC
tags:
  - Jquery
---
最近我的ASP.Net MVC Project 又遇到難題了

有時候因為希望可以建立一些功能給客戶選擇&#8230;  
選擇後可以按一下相對的按鈕來 Download file  
之前用ASP.Net時可以通過 Code-Behind來實現的

由於是要看看選擇了什麼才決定download 什麼東西  
我的想法是用Jquey 來把已選擇的條件用Ajax Post到 Controller上  
我的Controller是這樣的.. 為了方便做試驗我 Hard code Download File的位置

[csharp]  
[HttpPost]  
public ActionResult DownloadFile(string Filename)  
{  
return File(@"D:\UserProfile\Desktop\Img\MySQLMD5Function.png", "png/application", Filename);  
}  
[/csharp]

我的cshtml是

<pre>&lt;h2&gt;Non Ajax Post&lt;/h2&gt;
&lt;input type="button" value="NonAjaxPost" id="btn_NonAjaxPost" /&gt;</pre>

之後便可以在這個**Controller**上 輸出這個檔案

[javascript]  
$("#btn_NonAjaxPost").click(function () {  
$.post(&#8216;@Url.Action("DownloadFile", "NonAjaxPost")&#8217;, { Filename:"example.png" }, function () {  
});  
});  
[/javascript]

之後發現.. 好像不能用 **Ajax.Post** 或 **Ajax.Get** 來 **Download File**  
E.G. 不可以用**Jquery 的Ajax Post或Get 的動作** 連到一個 **Download File**的**Action** 來**Download**檔案.. [可能是因為Response 的Header 不能正確地 編譯 的關係]

最後終於想到了**解決方法**..  
就是要寫一個功能來令到到**JQuery**做一個 正常的**Post/Get**  
我們可以**Extend JQuery的 Library**

[javascript]  
<script type="text/javascript">  
$(document).ready(function () {  
(function($) {  
$.extend({  
//要做到Non-Ajax Get的話  
//我們可以使用  
//document.location = “我們想用get 去瀏覽到的URL 上” 之後再加進 要用的Parameter進去  
//其間我們使用這個功能時要放進2個Parameter 一個是 目的地的URL  
//另一個是 我們希望Post的 Parameter  
NonAjaxGet: function(url, params) {  
document.location = url + &#8216;?&#8217; + $.param(params);  
},  
//要做到Non-Ajax Post的話  
//我們可以使用JQuery/Javascript 來寫一個 暫用的Form來進行 之後用form.submit() 這個功能把Form Post進我們又Non-Ajax Post的頁面上  
//其間我們要放進2個Parameter 一個是 目的地的URL  
//另一個是 我們希望Post的 Parameter  
NonAjaxPost: function(url, params) {  
var $form = $("<form method=&#8217;POST&#8217;>").attr("action", url);  
$.each(params, function(name, value) {  
$("<input type=&#8217;hidden&#8217;>")  
.attr("name", name)  
.attr("value", value)  
.appendTo($form);  
});  
$form.appendTo("body");  
$form.submit();  
}  
});  
})(jQuery);  
});  
[/javascript]

**使用方法**:  
假設我們都是使用**JQuery**的

[javascript]  
// $.NonAjaxPost(&#8216;要POST 到的URL&#8217;, {  
// 變數: "變數值",變數2: "變數值2"  
// });

$("#btn_NonAjaxPost").click(function () {  
$.NonAjaxPost(&#8216;@Url.Action("DownloadFile", "NonAjaxPost")&#8217;, {  
Filename: "example.png"  
});  
});  
[/javascript]

這樣我便可以成功在ASP.Net MVC 使用JQuery來Download File了

Hope you find it useful