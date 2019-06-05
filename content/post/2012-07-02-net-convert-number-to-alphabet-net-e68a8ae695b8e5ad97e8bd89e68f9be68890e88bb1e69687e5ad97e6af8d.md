---
id: 2488
title: '.Net Convert Number to Alphabet &#8211; .Net 把數字轉換成英文字母'
date: 2012-07-02T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2488
permalink: '/2012/07/net-convert-number-to-alphabet-net-%e6%8a%8a%e6%95%b8%e5%ad%97%e8%bd%89%e6%8f%9b%e6%88%90%e8%8b%b1%e6%96%87%e5%ad%97%e6%af%8d/'
categories:
  - .Net Tips And Tricks
---
今天突然想到一個功能應該對寫**Sample Data** 十分有用的&#8230;  
因為有些時候我想Generate 一些看來有些意思的Data

原本想的功能是把**數字轉變成英**文 **Convert Number to Word**  
**E.G.**  
 **1 = One**  
 **2 = Two**  
很可惜&#8230; 想不到一個容易的的做法&#8230;  
這應該要自己寫一個小小的**Library**來做Reference才可以做到的..  
所以便在想**把數字變成英文字母**了  
**E.G.**  
 **1 = A**  
 **2 = B**  
 **26 = Z**

之後便寫了以下的一個功能了

[csharp]  
/// <summary>  
/// This function is use to convert Number to Alphabet  
/// </summary>  
/// <param name="Number">The Number has to be Between 1-26 where 1= A and 26 = Z</param>  
/// <param name="InUpperCase">This optional value Indicate whether the return string is Upper case or lower case</param>  
/// <returns>Aphabet which 1 = A and 26 = Z</returns>  
public static string ConvertNumberToAlphabet(int Number, bool InUpperCase = true)  
{  
if (Number <= 0 || Number > 26)  
{  
throw new Exception("The Number to be Convert to Alphabet has to be between 1-26");  
}  
//ACSII Code 65 represent Character A, therefore I Add 64 to the number to make 1 = A  
Number += 64;  
return InUpperCase ? ((char) Number).ToString() : ((char) Number).ToString().ToLower();  
}  
[/csharp]

**使用方法**十分簡單  
我們只需要執行這個功能.. 之後輸入**數字 1-26** 便可以把數字**轉換成 A-Z**了  
E.G.

[csharp]  
string Alphabet = ConvertNumberToAlphabet(1);  
Debug.WriteLine(Alphabet);  
[/csharp]

如果大家想**output 小揩**的話.. 可以把**IsUpper**這個變數變成**False**便可  
E.G.

[csharp]  
string Alphabet = ConvertNumberToAlphabet(1,false);  
Debug.WriteLine(Alphabet);  
[/csharp]

這個功能將會放進正成開發中的<a title="SCWLib" href="http://scwlib.codeplex.com/" target="_blank"><strong>SCWLib</strong> </a>歡迎大家使用

Hope you find it useful