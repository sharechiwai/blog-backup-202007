---
id: 3218
title: '.Net Get Last Day of Month &#8211; 如何在.Net上找出某一個月最後的一天是什麼'
date: 2014-06-08T00:00:36+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3218
permalink: '/2014/06/net-get-last-day-of-month-%e5%a6%82%e4%bd%95%e5%9c%a8-net%e4%b8%8a%e6%89%be%e5%87%ba%e6%9f%90%e4%b8%80%e5%80%8b%e6%9c%88%e6%9c%80%e5%be%8c%e7%9a%84%e4%b8%80%e5%a4%a9%e6%98%af%e4%bb%80%e9%ba%bc/'
categories:
  - .Net Tips And Tricks
---
今天寫的一個功能會以不同的設定產生不同的檔案名稱  
有時候會產生這個月最後一天的 **TimeStamp** E.g. **yyyyMMddd** **20140606**

之前介紹了如何在 **TSQL** 取得這個月最後的一天  
<a title="TSQL Get the last day of the month – TSQL 取得這個月最後的一天" href="http://blog.sharechiwai.com/2012/08/tsql-get-the-last-day-of-the-month-tsql-%e5%8f%96%e5%be%97%e9%80%99%e5%80%8b%e6%9c%88%e6%9c%80%e5%be%8c%e7%9a%84%e4%b8%80%e5%a4%a9/" target="_blank">TSQL Get the last day of the month – TSQL 取得這個月最後的一天</a>

今天想和大家分享如何在.Net上找出某一個月最後的一天是什麼

**解決方法**十分簡單..  
我們只需要知道想找到的那個月有多小天便可以..  
我們可以使用 **.Net**的 **DaysInMonth**(**Year**, **Month**)功能 來找出那個月有多少天  
之後再次建立一個新的**DateTime** Object便可以了  
E.G.

<pre>// Init Current Date
DateTime currentDate = DateTime.Now;
// Show Date
Console.WriteLine(string.Format("Current Date: {0:yyyyMMdd}",currentDate));

// Create a new DateTime object to store End Of Month
DateTime EndOfMonth = new DateTime(currentDate.Year, currentDate.Month, DateTime.DaysInMonth(currentDate.Year, currentDate.Month));
// Show Result
Console.WriteLine(string.Format("End of Month: {0:yyyyMMdd}",EndOfMonth));
</pre>

**結果**:  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3892/14258266700_cd723b04bb_z.jpg?resize=625%2C211" alt=".Net Get Last Day of Month" width="625" height="211" data-recalc-dims="1" /> 

Hope you find it useful