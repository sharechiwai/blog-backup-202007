---
id: 2836
title: '.Net Convert DateTime to TimeSpan &#8211; DateTime Object 轉換成 TimeSpan'
date: 2013-05-05T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2836
permalink: '/2013/05/net-convert-datetime-to-timespan-datetime-object-%e8%bd%89%e6%8f%9b%e6%88%90-timespan/'
categories:
  - .Net Tips And Tricks
tags:
  - TimeSpan
---
今天有一個Task 是要找出兩個日期中 相隔有多小個月&#8230;  
不知道為什麼我需要把**DateTime Object** 轉換成 **TimeSpan** 來做一些計算..

開始以為是很簡單的..  
誰不知試了很久都不能成功把**DateTime Object** 轉換成 **TimeSpan**

做了一會兒**Research**後終於找到了解決方法

**解決方法**:  
我們可以使用**DateTime Object**上的 Ticks 屬性 來 建立一個新的**TimeSpan Object**  
E.G.

[csharp]  
TimeSpan ts = new TimeSpan(DateTime.Now.Ticks);  
[/csharp]

Hope you find it useful