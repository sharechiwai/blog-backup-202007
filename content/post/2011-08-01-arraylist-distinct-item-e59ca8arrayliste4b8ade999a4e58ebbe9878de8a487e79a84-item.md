---
id: 1931
title: 'ArrayList Distinct Item &#8211; 在ArrayList中除去重複的 Item'
date: 2011-08-01T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1931
permalink: '/2011/08/arraylist-distinct-item-%e5%9c%a8arraylist%e4%b8%ad%e9%99%a4%e5%8e%bb%e9%87%8d%e8%a4%87%e7%9a%84-item/'
categories:
  - .Net Tips And Tricks
tags:
  - ArrayList to List
  - LINQ
---
今日有個朋友問..  
怎樣可以在一個**ArrayList中 找出Distinct的 Item**..  
E.G.**除去重複的 Item**.

**解決方法**有多個..其中一個是寫一個**For Loop**..  
當沒有重複時  
把ArrayList入面的Object 寫進去..

另外一個方法是使用**LINQ**

由於這是**ArrayList**的關係..  
所以不可以直接使用**List<>中的 LINQ** 功能

**解決方法**十分簡單..  
只需要把這個**ArrayList變成 List<>**  
之後再轉換成**ArrayList**便可  
E.G.  
**C#**

[csharp]  
//建立一些Dummy Data  
ArrayList ArrList=new ArrayList();  
ArrList.Add("1");  
ArrList.Add("2");  
ArrList.Add("1");  
ArrList.Add("1");  
ArrList.Add("3");

//建立一個新的ArrayList來儲存Distinct了的ArrayList的結果  
ArrayList newList = new ArrayList();  
//把ArrayList轉成Array..  
//之後使用Linq的方法Distinct這個Array..  
//最後把Distinct了的Array轉成Array 再用Add Range這個功能.把所有Array加進新的ArrayList上  
newList.AddRange(ArrList.ToArray().Distinct().ToArray());

//用以下的程式碼顯示結果  
for (int i = 0; i < newList.Count; i++)  
{  
MessageBox.Show(newList[i].ToString());  
}  
[/csharp]

Hope you find it useful