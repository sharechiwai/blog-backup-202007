---
id: 3442
title: 'How to show 2 Decimal Place in C# &#8211; 如何在C# 上把數字顯示為兩個小數位'
date: 2015-07-15T00:00:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3442
permalink: '/2015/07/how-to-show-2-decimal-place-in-c-%e5%a6%82%e4%bd%95%e5%9c%a8c-%e4%b8%8a%e6%8a%8a%e6%95%b8%e5%ad%97%e9%a1%af%e7%a4%ba%e7%82%ba%e5%85%a9%e5%80%8b%e5%b0%8f%e6%95%b8%e4%bd%8d/'
categories:
  - .Net Tips And Tricks
tags:
  - ASP.Net
  - ASP.Net MVC
---
今天的**ASP.Net MVC Application** 需要做一些數字格式化  
因為在**Database** 上他的 **DataType**是 **Money**  
當他們出現在**DataTable** 時顯示在**WebGrid**時便會變成 4個小數位  
**e.g. 10.0000**

如何在**C#** 上把數字顯示為兩個小數位呢?

**解決方法**十分簡單:  
我們,可以使用**String.Format** 來解決

<pre>decimal number = 0.1234567
string.Format("{0:0.00}", number)
</pre>

Hope you find it useful