---
id: 2095
title: Java Convert Int to String Convert Numeric to String
date: 2011-09-03T00:00:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2095
permalink: /2011/09/java-convert-int-to-string-convert-numeric-to-string/
categories:
  - Java
---
今天又繼續我**Android** 開發的生活了..  
又遇到一個難題&#8230;  
可能是因為經常使用**.Net**的關係&#8230;  
我以為把**Integer 轉成String** 是一個很簡單的 事&#8230;

**c#** &#8211; 使用**.ToString()** 便可以了

[csharp]  
int i = 8;  
string s = i.ToString();  
[/csharp]

因為 **Java**上也有 **toString**這個方法  
所以我便以為可以簡單地使用**.ToString**便可以了  
誰不知我便遇到以下的**Error**  
&#8220;<span style="color: #ff0000;"><strong>Cannot invoke toString() on the primitive type int</strong></span>&#8221;

原來在Java 上我們需要用到這個**Data Type** 的**Class** 來進行轉換的  
E.g **Integer.toString()**

[java]  
int i =0;  
String s = Integer.toString(i);  
[/java]

Hope you find it useful