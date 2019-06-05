---
id: 2491
title: ASP.Net MVC Javascript Alert ViewBag value
date: 2012-05-17T00:00:15+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2491
permalink: /2012/05/asp-net-mvc-javascript-alert-viewbag-value/
categories:
  - ASP.Net MVC
---
今天需要做用**Javascrpt** 的 **Alert** function 來彈出一些提示信息姶用戶..  
因為不同的用戶可能會收到不同的信息..  
而這些信息是Store 在**ASP.Net MVC**的**ViewBag**上&#8230;  
怎樣才可以在**Javascrript**上使用Alert來輸出 **ViewBag**的內容呢?

**解決方法**十分簡單

[javascript]  
<script type="text/javascript">  
var AlertMessage = &#8216;@(ViewBag.ShareChiWaiMessage)&#8217;;  
alert(AlertMessage);  
</script>  
[/javascript]

Hope you find it useful