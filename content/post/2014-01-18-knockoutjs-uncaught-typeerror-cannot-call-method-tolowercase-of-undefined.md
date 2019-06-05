---
id: 2999
title: 'KnockoutJs &#8211; Uncaught TypeError: Cannot call method &#8216;toLowerCase&#8217; of undefined'
date: 2014-01-18T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2999
permalink: /2014/01/knockoutjs-uncaught-typeerror-cannot-call-method-tolowercase-of-undefined/
categories:
  - KnockoutJS
tags:
  - KnockoutJS TroubleShooting
---
今天在學習**KnockoutJs**時 不知道為什麼常常出現這個這個錯誤信息  
&#8220;**<span style="color: #ff0000;">Uncaught TypeError: Cannot call method &#8216;toLowerCase&#8217; of undefined</span>** &#8221;  
[<img class="alignnone" alt="TypeError: Cannot call method 'toLowerCase' of undefined" src="https://i1.wp.com/farm8.staticflickr.com/7427/12120334664_81dc59f5a7_o.jpg?resize=517%2C35" width="517" height="35" data-recalc-dims="1" />](https://i1.wp.com/farm8.staticflickr.com/7427/12120334664_81dc59f5a7_o.jpg)  
我的**Model** 大概是這樣的

[javascript]  
var shareChiWaiViewModel = {  
sharechiwaiList =ko.observableArray([]),  
selectedfilter: ko.observable(),  
}

shareChiWaiViewModel.filteredItems = ko.computed(function() {  
var filter = this.selectedfilter().toLowerCase();  
/*  
* 還有很多還沒有整理好的Code  
* There are lots of mess code below&#8230;  
*/  
});

// Initial object&#8230;

// Bing Model  
ko.applyBindings(shareChiWaiViewModel);

[/javascript]

每當我**Refresh**時 都會出現  
&#8220;<span style="color: #ff0000;"><strong>Uncaught TypeError: Cannot call method &#8216;toLowerCase&#8217; of undefined</strong> </span>&#8221;  
我的 selectedfilter 應該是有value的..

經過了一段時間的Research  
終於發現了問題的所在  
原來是因為當Model的**selectedfilter** 還沒有 被assign value之前..  
已經執行了

[javascript]  
var filter = this.selectedfilter().toLowerCase();  
[/javascript]

所以便出現錯誤了

**解決方法**  
只是在定義**view model**時 先方一個**Empty string &#8220;&#8221;** 進這個 **observable**上便可以..  
**E.G.**

[javascript]  
selectedfilter: ko.observable(""),  
[/javascript]

Hope you find it useful