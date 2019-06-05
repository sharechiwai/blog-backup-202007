---
id: 2963
title: 'Convert Json to CSharp &#8212; 把Json轉換成 CSharp 的Object'
date: 2013-10-09T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2963
permalink: '/2013/10/convert-json-to-csharp-%e6%8a%8ajson%e8%bd%89%e6%8f%9b%e6%88%90-csharp-%e7%9a%84object/'
categories:
  - .Net Tips And Tricks
---
今天在電腦活動中..需要做一個功能去消化一些**JSON** 格式的資料..  
要把一**個JSON 的Response 轉換成一個C# 的Object** 以方便程式使用

一開始想自跟據所看到的**JSON Response** 來建立一些**.Net Class Object** 來解決這個問題

幸運地朋友介紹了一個很好用的網頁給我  
可以把**JSON Object** 轉換成 **CSharp Code**

大家有時間可以嘗試一下.. 十分好用的  
<a title="Convert Json to CSharp --- 把Json轉換成 CSharp 的Object" href="http://json2csharp.com/" target="_blank">http://json2csharp.com/</a>

只要把**JSON Code**貼上**TextBox** 之後按**Generate** 便可以很到你想要的**.Net Class Object**  
[json]  
{  
**<span style="color: #339966;">&#8220;sharefruit&#8221;: [</span>**  
** <span style="color: #339966;">{ &#8220;fruitName&#8221;:&#8221;Apple&#8221; , &#8220;price&#8221;:1.2 },</span>**  
** <span style="color: #339966;">{ &#8220;fruitName&#8221;:&#8221;Banana&#8221; , &#8220;price&#8221;:0.7 },</span>**  
** <span style="color: #339966;">{ &#8220;fruitName&#8221;:&#8221;Orange&#8221; , &#8220;price&#8221;:2.2 },</span>**  
** <span style="color: #339966;">]</span>**  
}  
[/json]

**CSharp Object**

[csharp]  
public class Sharefruit  
{  
public string fruitName { get; set; }  
public double price { get; set; }  
}

public class RootObject  
{  
public List sharefruit { get; set; }  
}  
[/csharp]

[<img class="alignnone size-full wp-image-2964" alt="json2csharp - generate c# classes from json" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/json2csharp-generate-c-classes-from-json-Google-Chrome.jpg?resize=625%2C534" width="625" height="534" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/json2csharp-generate-c-classes-from-json-Google-Chrome.jpg)  
Hope you find it useful