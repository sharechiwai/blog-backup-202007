---
id: 3284
title: 'Linq compare 2 lists &#8211; .Net Check if Items Not exist on current List &#8211; 如何在2個Lists 中找出和第二個List不相同的Item 項目'
date: 2014-07-25T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3284
permalink: '/2014/07/linq-compare-2-lists-net-check-if-items-not-exist-on-current-list-%e5%a6%82%e4%bd%95%e5%9c%a82%e5%80%8blists-%e4%b8%ad%e6%89%be%e5%87%ba%e5%92%8c%e7%ac%ac%e4%ba%8c%e5%80%8blist%e4%b8%8d%e7%9b%b8/'
categories:
  - .Net Tips And Tricks
tags:
  - LINQ
---
之前和大家介紹了怎樣可以找出在2個**List of String**上找出2個List 都有的 Item 出來

**今天想和大家介紹怎樣從兩個Lists 中找出 第一個List上 在第二個List裡面沒有的 Item**

我們可以使用 **List** 的<span style="color: #008000;"><strong>Except</strong> </span>功能

<pre>// Source List with String A,B,C,D,E
			List listA = new List();
            listA.Add("A");
            listA.Add("B");
            listA.Add("C");
            listA.Add("D");
            listA.Add("E");

			// List To Compare with String 1,A,4,E,5
            List listB = new List();
            listB.Add("1");
            listB.Add("A");
            listB.Add("4");
            listB.Add("E");
            listB.Add("5");

			// Retrieve the List of String which does not appear on the second List
            List matchList = listA.Except(listB).ToList().ForEach(Console.WriteLine);


</pre>

<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3911/14649453600_558ea181ce_z.jpg?resize=625%2C421" alt="Linq compare 2 lists - .Net Check if Items Not exist on current List - 如何在2個Lists 中找出和第二個List不相同的Item 項目 " width="625" height="421" data-recalc-dims="1" />  
Happy Coding