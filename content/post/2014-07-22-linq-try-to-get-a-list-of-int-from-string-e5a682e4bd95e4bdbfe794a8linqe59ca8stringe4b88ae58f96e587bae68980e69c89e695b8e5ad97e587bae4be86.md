---
id: 3282
title: 'LINQ try to get a list of int from string &#8211; 如何使用Linq在String上取出所有數字出來'
date: 2014-07-22T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3282
permalink: '/2014/07/linq-try-to-get-a-list-of-int-from-string-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8linq%e5%9c%a8string%e4%b8%8a%e5%8f%96%e5%87%ba%e6%89%80%e6%9c%89%e6%95%b8%e5%ad%97%e5%87%ba%e4%be%86/'
categories:
  - .Net Tips And Tricks
tags:
  - ASP.Net MVC
  - LINQ
  - WebGrid
---
今天要為同事解決一個 在**ASP.Net MVC** [**.Net**]將**String 轉成List of Int**的問題

情況是這樣的:  
公司的一個**ASP.Net MVC** 的Project 上..客戶會在 **WebGrid**上的**checkbox**上選擇需要的東西..  
我的同事便寫了一個隱藏的field 每當客戶選擇或取消選項時..  
他用了**Javascript** 來把數據**append** 到隱藏的field上  
他便用&#8221;|&#8221; 來把數據分隔  
但是我們還是要做一些**Validation**  
避免數據有問題時..會令到這個程式碼/程序出現問題  
E.G.  
&#8220;<span style="color: #008000;"><strong>1|ab|| | 3 |4|</strong></span>&#8221;  
**有空格或有字母時..當把數據轉到List Of Int時便會出現錯誤了**

由於他工作放大假中..  
所以我便要去解決他沒有解決的問題了  
就是用.net去把這一個 String轉成 List of Int..

開頭我都有一些不知如何是好..  
因為可以用一個比較簡單的方法..  
但是可能要寫多很多的程式碼  
就是先建立一個**String**的**Array**..  
之後用<span style="color: #008000;"><strong>Int.TryParse</strong></span>來把 成功認到是**Int**的 數據加進另一個**List of Int**上..  
感覺不太好..

做了一些research 之後終於找到解決方法了:  
**解決方法**:

我們可以嘗試使用**LINQ** 的方法去解決這個問題

<pre>// Input
  string tempInput = "1|ab|| | 3 |4|";

  // This value is used for int.TryParse reference
  int tempVal=0;
  List intList = (from i in tempInput.Split('|').ToList()
                                          where int.TryParse(i, out tempVal)
                                          select  int.Parse(i)).ToList();
  int noOfInt = intList.Count();
  // Output number of integer recognised 
  Console.WriteLine("No of Int: " + noOfInt.ToString());
  
  for(int i = 0; i&lt; intList.Count(); i++){
  	// Output the recognised integer one by one
  	Console.WriteLine(intList[i].ToString());
  }
  
</pre>

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5552/14834755584_119cfd53f0_z.jpg?resize=625%2C351" alt="Use Linq to extract List of Integer from string" width="625" height="351" data-recalc-dims="1" /> 

Happy Coding