---
id: 1988
title: '.Net Sorting Multiple properties in List of Object &#8211; .Net 上List of Object 以多項屬性進行排序'
date: 2011-08-20T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1988
permalink: '/2011/08/net-sorting-multiple-properties-in-list-of-object-net-%e4%b8%8alist-of-object-%e4%bb%a5%e5%a4%9a%e9%a0%85%e5%b1%ac%e6%80%a7%e9%80%b2%e8%a1%8c%e6%8e%92%e5%ba%8f/'
categories:
  - .Net Tips And Tricks
tags:
  - LINQ
---
最近有朋友問了一個很好的問題..  
在**List Of Object** 上 用**多過一個的屬性來排序**?

[csharp]  
//建立一個ShareChiWai_Model &#8211; 用來取一些Sample的List Data  
ShareChiWai\_Model Share\_Model = new ShareChiWai_Model();  
//這個例子我們使用Get\_Food\_List() 的資料..因為有很多屬性可以用來示範  
List<Food> FoodList = Share\_Model.Get\_Food_List();  
//我們可以用FoodList.sort() 這個功能來做 Sorting 可惜只可以 以一個屬性來排序  
FoodList.Sort(delegate(Food f1, Food f2) { return f1.Price.CompareTo(f2.Price); });  
//再次使用 的時候只會以 最後排序的屬性來排序  
FoodList.Sort(delegate(Food f1, Food f2) { return f1.Price.CompareTo(f2.Price); });  
dgv_Data.DataSource = FoodList;  
[/csharp]

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/aa492fab68594bd49347210c2e1f8b87/renditions/fullsize.jpg?resize=600%2C391" alt="Sort() cannot solve .Net Sorting Multiple properties in List of Object" width="600" height="391" data-recalc-dims="1" /> 

我比較喜歡使用**LINQ**..感覺得方便..  
用**LINQ** 可以很方便地解決這個問題

**解決方法**:  
我們可以使用**List.OrderBy** 和 **ThenBy** 來解決這個問題  
E.G.

[csharp]  
//下面的例子我用了Order By Decending Order因為這樣子會容易一點看到效果  
FoodList = FoodList.OrderByDescending(f => f.Price).ThenBy(f => f.Food_Name).ToList();  
//由於 OrderBy/OrderByDescending/ThenBy/ThenByDescending IOrderedEnumerable<TSource> 的關係..所以我們要用ToList()來把他轉回做 List  
[/csharp]

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/21cfdf37c83b4477b8859e7f8607425e/renditions/fullsize.jpg?resize=603%2C397" alt=".Net Sorting Multiple properties in List of Object  work with LINQ" width="603" height="397" data-recalc-dims="1" />  
Hope you find it useful