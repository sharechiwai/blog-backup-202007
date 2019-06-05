---
id: 3491
title: '.Net How to Add slash correctly for Path &#8211; 如何安全地建立資料夾路徑'
date: 2015-09-02T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3491
permalink: '/2015/09/net-how-to-add-slash-correctly-for-path-%e5%a6%82%e4%bd%95%e5%ae%89%e5%85%a8%e5%9c%b0%e5%bb%ba%e7%ab%8b%e8%b3%87%e6%96%99%e5%a4%be%e8%b7%af%e5%be%91/'
categories:
  - .Net Tips And Tricks
tags:
  - .Net Troubleshooting
---
公司需要寫了一個小小的**Document Repository** 的功能

還記得之前自己經驗有時候使用者會把他們輸入的路徑會有&#8221;**/**&#8220;.. 但是有時卻沒有  
所以我之前便寫了一個很無聊的功能 **AddSlash**.. 去檢查 User Input是不是以 **/** 來開首或結尾..  
之後再幫這個User Input 適當地加上 Slash

最近發現原來**.Net Framework**自己已經有一個很好用的功能  
叫 <span style="color: #008000;"><strong>Path.combine.</strong></span> 你可以把**Path** 放進他的變數內..  
之後他便會幫你建立你的**Path**/**路徑**了

E.G.

<pre>using System;
					
public class Program
{
	public static void Main()
	{
		string driveLetter = @"D:\";
		string folder1 = "Data";
		string folder2 = @"Files\";
	    string folder3 = @"sharechiwai";
		string t = System.IO.Path.Combine(driveLetter, folder1, folder2,folder3);
		
		// Return output
		Console.WriteLine(t);
	}
}
</pre>

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5815/19943849554_010b03f488_z.jpg?resize=625%2C216" alt=".Net Path.Combine function" width="625" height="216" data-recalc-dims="1" /> Hope you find it useful