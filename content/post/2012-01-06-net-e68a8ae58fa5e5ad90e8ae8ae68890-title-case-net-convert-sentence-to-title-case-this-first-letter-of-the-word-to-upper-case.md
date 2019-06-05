---
id: 2221
title: '.Net 把句子變成 Title Case &#8211; .Net convert sentence to Title Case (This first Letter of the Word to Upper Case)'
date: 2012-01-06T00:00:34+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2221
permalink: '/2012/01/net-%e6%8a%8a%e5%8f%a5%e5%ad%90%e8%ae%8a%e6%88%90-title-case-net-convert-sentence-to-title-case-this-first-letter-of-the-word-to-upper-case/'
categories:
  - .Net Tips And Tricks
tags:
  - Text Function
---
最近有一個任務..就是是要把一些 地址從大寫字母轉成 **Title Case**  
E.g.  
**WELCOME TO SHARECHIWAI**  
轉成  
**Welcome To Sharechiwai**  
由為把他們insert入 Invoice上會有點怪怪的&#8230;  
我第一個想到的方法是用 **Excel**上的**ProperCase**  
但是如果可以寫一個程式來轉換便更好了&#8230;

解決方法十分簡單  
我們可以使用**TextInfo**的 **ToTitleCase** 這個功能去把文字轉換成Title Case E.G. 一個句子上的每個詞語上的第一個字母轉成大揩..其他的會轉換成小揩

[csharp]  
string SampleText ="welcome to sharechiwai"  
System.Globalization.CultureInfo.CurrentUICulture.TextInfo.ToTitleCase(SampleText);  
[/csharp]

**溫馨提示**:  
由於這個功能遇到詞語上所有字都是大揩的話&#8230;這個功能不能打這些字轉成**Title Case**的  
所以我會建議大家用**.ToLower()**這個功能先把字母轉戶細揩&#8230;以方便轉成**Title Case**

[csharp]  
Console.WriteLine("Original Text");  
string OriginalText = "HELLO, WELCOME TO SHARECHIWAI";  
Console.WriteLine(OriginalText);  
Console.WriteLine();//newline

//Use Title Case from Original UpperCase Text  
Console.WriteLine("Original UpperCase Text to TitleCase");  
string TitleCaseInOriginalText =  
System.Globalization.CultureInfo.CurrentUICulture.TextInfo.ToTitleCase(OriginalText);  
Console.WriteLine(TitleCaseInOriginalText);  
Console.WriteLine();//newline

//Original To LowerCase then TitleCase  
Console.WriteLine("Original To LowerCase then TitleCase");  
string TitleCaseInLowerCaseOriginalText =  
System.Globalization.CultureInfo.CurrentUICulture.TextInfo.ToTitleCase(OriginalText.ToLower());  
Console.WriteLine(TitleCaseInLowerCaseOriginalText);  
[/csharp]

**Result**  
&#8212;&#8212;-  
<span style="color: #339966;">Original Text</span>  
 <span style="color: #339966;">HELLO, WELCOME TO SHARECHIWAI</span>

<span style="color: #339966;">Original UpperCase Text to TitleCase</span>  
 <span style="color: #339966;">HELLO, WELCOME TO SHARECHIWAI</span>

<span style="color: #339966;">Original To LowerCase then TitleCase</span>  
 <span style="color: #339966;">Hello, Welcome To Sharechiwai</span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/adcd737e8d4141508362f7894fb45b7a" alt="Sample output for convert text to TitleCase" width="810" height="738" /> 

Hope you find it useful