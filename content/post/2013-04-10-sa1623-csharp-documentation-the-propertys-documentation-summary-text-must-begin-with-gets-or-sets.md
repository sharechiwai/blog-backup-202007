---
id: 2734
title: 'SA1623 : CSharp.Documentation : The property&#8217;s documentation summary text must begin with: Gets or sets'
date: 2013-04-10T00:00:29+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2734
permalink: /2013/04/sa1623-csharp-documentation-the-propertys-documentation-summary-text-must-begin-with-gets-or-sets/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
今天遇到的另一個**StyleCop** 警告是  
&#8220;<span style="color: #ff0000;"><strong>SA1623 : CSharp.Documentation : The property&#8217;s documentation summary text must begin with: Gets or sets</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2735" alt="SA1623 : CSharp.Documentation : The property's documentation summary text must begin with: Gets or sets" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1623.jpg?resize=374%2C77" width="374" height="77" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1623.jpg)

[csharp]  
/// <summary>  
/// <strong>Date Of Entry</strong>  
/// </summary>  
public string DOE { get; set; }

[/csharp]

**解決方法**  
在 [**Summary**] 是要使用 &#8220;**Gets or sets**&#8221; 來開首的.. 即使大小寫不同也會出現上面的警告信息  
E.G.

[csharp]  
/// <summary>  
///<strong> Gets or sets Date Of Entry</strong>  
/// </summary>  
public string DOE { get; set; }

[/csharp]

Hope you find it useful