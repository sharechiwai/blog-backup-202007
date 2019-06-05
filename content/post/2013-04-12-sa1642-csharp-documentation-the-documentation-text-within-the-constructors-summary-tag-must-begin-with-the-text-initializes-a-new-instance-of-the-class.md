---
id: 2743
title: 'SA1642 : CSharp.Documentation : The documentation text within the constructor&#8217;s summary tag must begin with the text: Initializes a new instance of the <see cref="MainPage" /> class.'
date: 2013-04-12T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2743
permalink: /2013/04/sa1642-csharp-documentation-the-documentation-text-within-the-constructors-summary-tag-must-begin-with-the-text-initializes-a-new-instance-of-the-class/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
今天繼續嘗試把正在開始開發的**Windows Phone 8 App**的程式碼符合**StyleCop**的規定  
當我使用**StyleCop** 檢查我的程式碼時出現了很多警告  
E.G.

&#8220;<span style="color: #ff0000;"><strong>SA1642 : CSharp.Documentation : The documentation text within the constructor&#8217;s summary tag must begin with the text: Initializes a new instance of the class.</strong></span>&#8221;

以下是我寫在**Constructor**上寫的**Comment**

[csharp]  
/// <summary>  
/// <strong>This is the constructor of this class</strong>  
/// </summary>  
public MainPage()  
{  
InitializeComponent();

// Sample code to localize the ApplicationBar  
//BuildLocalizedApplicationBar();  
}  
[/csharp]

誰不知..**Style Cop** 的規定是要在**Constructor** 上寫以以下的寫句開頭&#8230;  
&#8220;**Initializes a new instance of the class**.&#8221;

[csharp]  
/// <summary>  
/// <strong>Initializes a new instance of the <see cref="</strong>MainPage<strong>" /> class</strong>  
/// and predefine variable settings and check &#8230;etc  
/// </summary>  
public MainPage()  
{  
InitializeComponent();

// Sample code to localize the ApplicationBar  
//BuildLocalizedApplicationBar();  
}  
[/csharp]

Happy Coding