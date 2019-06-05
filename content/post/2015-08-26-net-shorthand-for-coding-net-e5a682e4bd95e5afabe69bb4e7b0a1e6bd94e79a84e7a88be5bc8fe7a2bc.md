---
id: 3485
title: '.Net Shorthand for coding  &#8211; .Net 如何寫更簡潔的程式碼'
date: 2015-08-26T20:06:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3485
permalink: '/2015/08/net-shorthand-for-coding-net-%e5%a6%82%e4%bd%95%e5%af%ab%e6%9b%b4%e7%b0%a1%e6%bd%94%e7%9a%84%e7%a8%8b%e5%bc%8f%e7%a2%bc/'
categories:
  - .Net Tips And Tricks
tags:
  - Best Practices
---
在寫新的**Module**時候感到自己之前寫的 程式碼比較長..  
太多變數..所以有時會令到可讀性減低  
所以便決定用一個更簡潔的方法去寫我的程式碼..

今日想和大家分享的是如果用**ShortHand**的方法寫一些  
**+-*/既 operator**

我們可用  
variable [**Operator** e.g. **+-*/**] = 另一個 variable

**E.G.**

<pre>using System;

public class Program
{
	public static void Main()
	{
		// Declare Variable i
		int i = 100;
		
		// Assign  variable
		i = i + 1;
		Console.WriteLine(i.ToString());
		
		// shorthand apply +-*/ to variable
		i -= 10;
		Console.WriteLine(i.ToString());
		
		// Assign variable to -10
		i =-10;
		Console.WriteLine(i.ToString());
	}
}
</pre>

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5781/20528360481_ae293bd7c8_z.jpg?resize=625%2C354" alt=".Net ShortHand Operator" width="625" height="354" data-recalc-dims="1" />  
Hope you find it useful