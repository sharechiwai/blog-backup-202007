---
id: 2985
title: 'Check if KnockoutJs is loaded &#8211; 檢查KnockoutJS 是否已經安裝'
date: 2014-01-08T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2985
permalink: '/2014/01/check-if-knockoutjs-is-loaded-%e6%aa%a2%e6%9f%a5knockoutjs-%e6%98%af%e5%90%a6%e5%b7%b2%e7%b6%93%e5%ae%89%e8%a3%9d/'
categories:
  - KnockoutJS
tags:
  - KnockoutJS
  - MVVM
---
最近終於開始了 學習 **KnockoutJs**&#8230;  
希望可以好好運用**KnockoutJs** 來學 **MVVM** 這個Concept  
之後可以能在其他的Application上應該**MVVM**  
第一個步驟..當然是檢查一下 **KnockoutJs** 是否已經安裝在你的網頁上..  
E.G. 只否可以在你的網頁你使用**Knockout** JS

以下是我測試的放法  
檢查網頁上有沒有 **window.ko 這個Object**  
如果是&#8221;**undefined**&#8221; 的話&#8230;你的**KnockoutJs Library** 應該是沒有安裝好

[javascript]  
<script src="/Scripts/knockout-3.0.0.js" type="text/javascript"></script>

<script type="text/javascript">  
if (typeof (window.ko) == "object") {  
alert("Knockoutjs loaded");  
} else {  
alert("Knockoutjs not loaded");  
}  
// return "undefined" &#8211; if Knockoutjs is not loaded  
// return "object" &#8211; if Knockoutjs is loaded  
alert(typeof (window.ko));  
</script>  
[/javascript]

Hope you find it useful