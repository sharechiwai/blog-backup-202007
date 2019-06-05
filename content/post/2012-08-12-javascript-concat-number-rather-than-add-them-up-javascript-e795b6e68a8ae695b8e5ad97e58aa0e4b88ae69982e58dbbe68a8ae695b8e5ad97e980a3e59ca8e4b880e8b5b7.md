---
id: 2539
title: 'Javascript Concat Number as string rather than add them up &#8211; Javascript 當把數字加上時卻把數字連在一起'
date: 2012-08-12T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2539
permalink: '/2012/08/javascript-concat-number-rather-than-add-them-up-javascript-%e7%95%b6%e6%8a%8a%e6%95%b8%e5%ad%97%e5%8a%a0%e4%b8%8a%e6%99%82%e5%8d%bb%e6%8a%8a%e6%95%b8%e5%ad%97%e9%80%a3%e5%9c%a8%e4%b8%80%e8%b5%b7/'
categories:
  - Javascript
---
今天在公司其中一Project上使用**Javascript**來計算時出現了一個問題  
測試的同事問..為什麼數是會多了一個 0  
像是計算時有些問題..  
叫我去看看..  
我看了自己的程式碼好幾次..  
最後要慢慢一步一步來Debug才找到出現問題的地方

問題頁來出現在**Javascript** 處理數字上  
E.G.

[javascript]  
var i = $("#txt_Input1").val(); //100  
var j = $("#txt_Input2").val(); //0  
alert(i+j);  
[/javascript]

**結果卻變成了 1000**

問題是因為當 javascript 讀取TextBox的資料的時候  
當了他們是文字.. 而Javascript上的&#8221;+&#8221; 可以代表是 Concat 字串..  
所以便把 0 加上了100 上變成了1000 了

**解決方法**:  
我們可以使用 parseInt 或 parseFloat 來把字轉成數值  
之後便可以正常地把 100 加上0 變成100 了

**E.G**.

[javascript]  
var i = $("#txt_Input1").val(); //100  
var j = $("#txt_Input2").val(); //0  
alert(parseFloat(i)+parseFloat(j));  
[/javascript]

Hope you find it useful