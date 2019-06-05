---
id: 4020
title: 'Csharp &#8211; Remove last comma &#8211; C# 如何移除最後一個符號 (分號)?'
date: 2017-07-10T07:02:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4020
permalink: '/2017/07/csharp-remove-last-comma-c-%e5%a6%82%e4%bd%95%e7%a7%bb%e9%99%a4%e6%9c%80%e5%be%8c%e4%b8%80%e5%80%8b%e7%ac%a6%e8%99%9f-%e5%88%86%e8%99%9f/'
categories:
  - .Net Tips And Tricks
tags:
  - dotnet tips and tricks
---
**解決方法**十分簡單  
我們可以使用 [<img class="alignnone size-full wp-image-4021" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png?resize=625%2C314" alt="C# remove last comma (string.TrimEnd)" width="625" height="314" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png?w=920 920w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png?resize=300%2C151 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png?resize=768%2C386 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png?resize=624%2C313 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/removeComma.png) 這個功能來解決這個問題

E.G.

<pre>string y = "1,2,3,4,5,6,";
Console.WriteLine(y.TrimEnd(','));
</pre>

Hope you find it useful