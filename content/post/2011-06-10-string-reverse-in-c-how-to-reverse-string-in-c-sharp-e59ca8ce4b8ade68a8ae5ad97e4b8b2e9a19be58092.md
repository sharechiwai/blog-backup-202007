---
id: 1807
title: 'String.Reverse in C# &#8211; How to reverse string in c Sharp &#8211; 在C#中把字串顛倒'
date: 2011-06-10T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1807
permalink: '/2011/06/string-reverse-in-c-how-to-reverse-string-in-c-sharp-%e5%9c%a8c%e4%b8%ad%e6%8a%8a%e5%ad%97%e4%b8%b2%e9%a1%9b%e5%80%92/'
categories:
  - .Net Tips And Tricks
---
今日朋友問了我一個很有趣的問題  
我很想和大家分享..  
為了讓大家可以思考一下  
不讓大家可以直接把答案看到..  
所以希望可以把答案倒轉寫出來..  
**問題是這樣的**  
**1) What do you call a deer with no eyes**  
**2) What do you call a deer with no eyes and no legs**

知道答案既朋友可以留找言給我 =P

我這位朋友比較有創造性的  
想住他將來會繼續問我這些有趣問題的  
最後我還是為了方便自己..寫了一個小小的**Silverlight App**  
來把**字串顛倒 Reverse String.**

之後發現原來**C#**是沒有**String.Reverse** 這個功能的  
所以最後還是要自己寫一些Code來實現這個功能

**解決方法:**  
**C#**

[csharp]  
string StringToReverse = "blog.sharechiwai.com";  
char[] TempString = StringToReverse .ToCharArray();  
Array.Reverse( TempString );  
MessageBox.Show(new string( TempString ));  
[/csharp]

有關**VB.NET** 的把文字倒轉 方法可以參考以下考學  
**<a title="VB.net String Reverse — VB.Net 把文字倒轉" href="http://blog.sharechiwai.com/2010/08/vb-net-string-reverse-vb-net-%E6%8A%8A%E6%96%87%E5%AD%97%E5%80%92%E8%BD%89/" target="_blank">VB.net String Reverse — VB.Net 把文字倒轉</a>**

Hope you find it useful