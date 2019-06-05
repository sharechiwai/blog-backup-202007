---
id: 511
title: 'VB.net String Reverse &#8212; VB.Net 把文字倒轉'
date: 2010-08-27T07:00:22+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=511
permalink: '/2010/08/vb-net-string-reverse-vb-net-%e6%8a%8a%e6%96%87%e5%ad%97%e5%80%92%e8%bd%89/'
jabber_published:
  - "1282864448"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282889747";}";'
categories:
  - .Net Tips And Tricks
---
今天想學習用**.Net 4**寫一個簡單的**WCF Web service**, 所以便想這個Web Service 把我所傳入[input]的string 把他倒轉[return]輸出來&#8230;

之後才發現原來不可以直接用**String.Reverse()** 這個功能的

**例如:**  
[vb]  
Dim InputString As String =abc  
MsgBox(InputString.Reverse.ToString, MsgBoxStyle.Information)  
[/vb]  
結果會是這樣的  
[<img class="alignnone size-full wp-image-514" title="reverseString" src="https://i1.wp.com/farm6.static.flickr.com/5223/5687813205_cfd706e739.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5223/5687813205_cfd706e739.jpg)

**解決方法&#8212;十分簡單**  
原來VB.Net 有一個功能的叫 &#8220;**StrReverse**&#8221;  
大家可以使用這個功來做到**String Reverse/ 把文字倒轉 的效果**  
E.G.  
[vb]  
Dim InputString As String =abc  
MsgBox(StrReverse(InputString), MsgBoxStyle.Information)  
[/vb]  
[<img class="alignnone size-full wp-image-513" title="cba" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/17a9627b9c2248acac3bd17218e424ff" alt="" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/17a9627b9c2248acac3bd17218e424ff)

Hope you find it useful