---
id: 3280
title: 'Linq compare 2 lists &#8211; .Net Check if Items exist on Both Lists &#8211; .Net如何在2個Lists 中找出相同的Item 項目'
date: 2014-07-20T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3280
permalink: '/2014/07/linq-compare-2-lists-net-check-if-items-exist-on-both-lists-net%e5%a6%82%e4%bd%95%e5%9c%a82%e5%80%8blists-%e4%b8%ad%e6%89%be%e5%87%ba%e7%9b%b8%e5%90%8c%e7%9a%84item-%e9%a0%85%e7%9b%ae/'
categories:
  - .Net Tips And Tricks
tags:
  - LINQ
---
今天需要寫一個功能去看看**2個** **List of String** 上有那些**String** 是2個Lists內都有的

做了一會research後 終於找到解決方法了

我們可以使用 **List** 的<span style="color: #008000;"><strong>Intersect</strong> </span>功能

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3871/14649534178_86838647ee_z.jpg?resize=625%2C461" alt="Linq - to get matched item from 2 lists of string" width="625" height="461" data-recalc-dims="1" /> 

**E.G.**

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

          			// Retrieve the List of String which appear on both List
            List matchList = listA.Intersect(listB).ToList();

            for (int i = 0; i &lt; matchList.Count; i++)
            {
               			// Output the list of matched string
                Console.WriteLine(matchList[i]);
            }
</pre>

Happy Coding