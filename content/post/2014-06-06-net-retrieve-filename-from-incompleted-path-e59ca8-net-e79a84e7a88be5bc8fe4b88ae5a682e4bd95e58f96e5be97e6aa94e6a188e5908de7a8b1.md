---
id: 3216
title: '.Net Retrieve Filename from Incompleted Path &#8211; 在.Net 的程式上如何取得檔案名稱'
date: 2014-06-06T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3216
permalink: '/2014/06/net-retrieve-filename-from-incompleted-path-%e5%9c%a8-net-%e7%9a%84%e7%a8%8b%e5%bc%8f%e4%b8%8a%e5%a6%82%e4%bd%95%e5%8f%96%e5%be%97%e6%aa%94%e6%a1%88%e5%90%8d%e7%a8%b1/'
categories:
  - .Net Tips And Tricks
---
之前幫公司寫個**FTP Module**..  
發現不同的Library輸出的Filename 都有點不一樣的..  
有些輪出全個**Full file path** and **filename**  
有些會出現**Relative path**  
有些只出現檔案名稱

所以我便嘗試自行寫一個功能出來找出他們輸出的檔案名稱了..  
誰不知&#8230;因為有太多不同的**Combination** 的關係..所以不太成功..  
做了一會research 之後發現  
解決方法十分簡單..

**解決方法**  
我們可以使用 **.Net Framework**中的 **Path.GetFileName(**&#8220;檔案名稱 variable&#8221;**)**;  
便可以取得檔案名稱了

E.G.

<pre>// Full File Path -&gt; 輸出: file.txt
string filename1 = @"d:\sharechiwai\file.txt";
Console.WriteLine("File1: " + Path.GetFileName(filename1));

// Full Network File Path -&gt; 輸出: file2.txt
string filename2 = @"\\sharechiwai\file2.txt";
Console.WriteLine("File2: " + Path.GetFileName(filename2));

// Just file -&gt; 輸出: index.php
string filename3 = "index.php";
Console.WriteLine("File3: " + Path.GetFileName(filename3));

// Web link -&gt; 輸出: index.php
string webFile = "http://sharechiwai.com/index.php";
Console.WriteLine("Web File: " + Path.GetFileName(webFile));
</pre>

**結果**:  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5531/14257784359_0771333680_z.jpg?resize=474%2C499" alt=".Net GetFileName Sample Code" width="474" height="499" data-recalc-dims="1" /> 

Hope you find it useful