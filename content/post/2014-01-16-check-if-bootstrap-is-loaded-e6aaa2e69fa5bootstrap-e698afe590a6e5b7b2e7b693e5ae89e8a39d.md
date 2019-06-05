---
id: 2996
title: 'Check if Bootstrap is loaded &#8211; 檢查Bootstrap 是否已經安裝'
date: 2014-01-16T00:00:41+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2996
permalink: '/2014/01/check-if-bootstrap-is-loaded-%e6%aa%a2%e6%9f%a5bootstrap-%e6%98%af%e5%90%a6%e5%b7%b2%e7%b6%93%e5%ae%89%e8%a3%9d/'
categories:
  - Javascript
tags:
  - bootstrap
---
在嘗試使用**Bootstrap**的時候  
又不知道自己的網頁上是成功地Load了 **Bootstrap**  
大家可以嘗試使用以下的方法

檢查網頁上有沒有<span style="color: #339966;"><strong> $.fn.modal</strong></span>這個**function**  
如果是執行 <span style="color: #339966;"><strong>alert(typeof ($.fn.modal))</strong></span> 時 他的結果是&#8221;<span style="color: #ff0000;"><strong>undefined</strong></span>&#8221; **Bootstrap Library** 應該是沒有安裝好

**E.G.**

[javascript]  
<script src="//netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js"></script>

<script type="text/javascript">  
if (typeof ($.fn.modal) == "function") {  
alert("Bootstrap loaded");  
} else {  
alert("Bootstrap not loaded");  
}  
// return "undefined" &#8211; if bootstrap is not loaded  
// return "function" &#8211; if bootstrap is loaded  
alert(typeof ($.fn.modal));  
</script>  
[/javascript]

Hope you find it useful