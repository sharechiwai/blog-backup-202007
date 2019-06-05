---
id: 3195
title: 'CSharp Get Day Of Week in Int &#8211; 如何在.Net上取得今天是星期幾以數字表達'
date: 2014-05-25T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3195
permalink: '/2014/05/csharp-get-day-of-week-in-int-%e5%a6%82%e4%bd%95%e5%9c%a8-net%e4%b8%8a%e5%8f%96%e5%be%97%e4%bb%8a%e5%a4%a9%e6%98%af%e6%98%9f%e6%9c%9f%e5%b9%be%e4%bb%a5%e6%95%b8%e5%ad%97%e8%a1%a8%e9%81%94/'
categories:
  - .Net Tips And Tricks
---
今天在公司的一個程式有一個設定..  
就是不同的客戶可以在不同的日子[星期一 至星期日 任由他們設定] 收到報告..

所以在程式上需要一個功能去決定今天是星期幾.. 之後再決定對比一些客戶的資料庫設定

如何在**.Net**上取得今天是星期幾以數字表達

**解決方法**十分簡單

如果我們用 <span style="color: #008000;"><strong>DateTime.Now</strong></span> 來取得今天的日期  
之後使用 <span style="color: #008000;"><strong>DayOfWeek</strong> </span>屬性 來取得今天是星期幾

**E.G.**

<pre>// This return Thursday, as it is Thursday today / 結果是Thursday因為今天是星期四
Console.WriteLine(DateTime.Now.DayOfWeek);

// This return 4, as we cast the result to integer / 結果是4因為星期一是1
Console.WriteLine(Convert.ToString((int)DateTime.Now.DayOfWeek));
</pre>

<div style="width: 650px" class="wp-caption alignnone">
  <img src="https://i0.wp.com/farm6.static.flickr.com/5553/14377726596_8cef4264f8_z.jpg?resize=625%2C312" alt="" width="625" height="312" data-recalc-dims="1" />
  
  <p class="wp-caption-text">
    .Net Get Current Date&#8217;s Day of Week in Number
  </p>
</div>

Hope you find it useful