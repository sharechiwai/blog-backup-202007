---
id: 2865
title: '.Net Calculate number of days between two dates &#8211; .Net 上如何找出兩個日期上有多少天?'
date: 2013-05-12T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2865
permalink: '/2013/05/net-calculate-number-of-days-between-two-dates-net-%e4%b8%8a%e5%a6%82%e4%bd%95%e6%89%be%e5%87%ba%e5%85%a9%e5%80%8b%e6%97%a5%e6%9c%9f%e4%b8%8a%e6%9c%89%e5%a4%9a%e5%b0%91%e5%a4%a9/'
categories:
  - .Net Tips And Tricks
---
今天公司上的其中一個**ASP.Net MVC Project**上需要在**ASP.Net的Page**上面做一個些**If Statement**去判斷不同日子來設定不同的**Status**

但是怎樣可以在**.Net**上計算出兩個日期上有多少天呢?  
做了一會research 之後終於找到了解決方法

我們可以使用 **DateTime Class**上的 **TotalDays**這個屬性  
來找出日期有多少天..

**E.G.**

[csharp]  
// First Date  
DateTime firstDate = new DateTime(2013, 1,1);

//Second Date  
DateTime secondDate = new DateTime(2013, 3, 1);

//由於 TotalDays 這個屬性 會Return double的關係..所以我用了 Math.ceiling這個方法來把 TotalDays的結果 Round up  
MessageBox.Show(Math.Ceiling((secondDate &#8211; firstDate).TotalDays).ToString());  
[/csharp]

Hope you find it useful