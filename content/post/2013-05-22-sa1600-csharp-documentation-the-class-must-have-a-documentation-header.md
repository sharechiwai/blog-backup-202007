---
id: 2908
title: 'SA1600 : CSharp.Documentation : The class must have a documentation header.'
date: 2013-05-22T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2908
permalink: /2013/05/sa1600-csharp-documentation-the-class-must-have-a-documentation-header/
categories:
  - StyleCop
---
今天遇到的 **StyleCop Warning**是這一個  
&#8220;<span style="color: #ff0000;"><strong>SA1600 : CSharp.Documentation : The method must have a documentation header.</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2909" alt="SA1600 : CSharp.Documentation : The method must have a documentation header." src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1600.png?resize=540%2C100" width="540" height="100" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1600.png)

當剛剛建立完一個**function** 之後便會出現..  
原因是因為沒有 **documentation header** 去解釋這一個功能有什麼作用  
和他的變數代表什麼  
還有會**return**出來的是什麼等等

[csharp]  
public string SayHello(string yourName)  
{  
return "Hello " + yourName;  
}  
[/csharp]

解決方法十分簡單  
只是填上 這個功能的**Summary** 和 **Parameter** 是什麼東西 和 **Return**什麼便可以

**解決方法:**  
**E.G.**

[csharp]  
/// <summary>  
/// This function is use to say hello to the input [yourName]  
/// </summary>  
/// <param name="yourName">The name to say Hello to</param>  
/// <returns>return "Hello the input name"</returns>  
public string SayHello(string yourName)  
{  
return "Hello " + yourName;  
}  
[/csharp]

[<img class="alignnone size-full wp-image-2910" alt="SA1600 : CSharp.Documentation : The method must have a documentation header. (Solved)" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1600Fix.png?resize=614%2C214" width="614" height="214" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1600Fix.png)  
Hope you find it useful