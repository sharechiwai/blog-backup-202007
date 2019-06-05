---
id: 1904
title: 'Convert DataTable to List of Object &#8211; 把DataTable轉成List Of Object'
date: 2011-07-21T00:00:43+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1904
permalink: '/2011/07/convert-datatable-to-list-of-object-%e6%8a%8adatatable%e8%bd%89%e6%88%90list-of-object/'
categories:
  - ASP.Net MVC
tags:
  - Convert DataTable to List Of Object
  - LINQ to Object
  - ShareChiWai_Model
---
學習**ASP.Net MVC 3** 的挑戰開始了&#8230;  
之前使用**ASP.Net Web Application** 時很多時候都是使用DataTable的  
[使用**DataAdapter** 來取得資料..之後再把資料放進**Drop Down List, GridView**等 控件上]  
但是在**MVC** 行多時候都會用到**Model** 的&#8230; [好像是沒有**DataTable的概念**&#8230;]

可惜**DataTable** 是沒有一個method 可以直接**把DataTable 轉成一個List of Object**的  
我想到的其中一個方法是寫一個**ForLoop**之後 把資料一個一個地取出..  
之後再建立一個**Object**..之後再把這個Object 加到這個List 上

以下的Sample會用到我之前所建立的**Dummy DataTable** 的Class 來**populate**這些**DataTable**的data

由於我們要建立一個**Object**的關係..  
我們先要準備一個**Class**來建立一個Object 儲存每一個**DataRow**的資料..  
之後把這些**Object 都加進List** 上

**E.G.**  
**C#**

[csharp]  
ShareChiWai\_Model Share\_ChiWai = new ShareChiWai_Model();  
DataTable tbl = Share\_ChiWai.Get\_Food_Tbl();

List<Food> Food_List = new List<Food>();  
for (int i = 0; i < tbl.Rows.Count; i++)  
{  
Food_List.Add(new Food()  
{  
Food\_ID = (string)tbl.Rows\[i\]\["Food\_ID"\],  
Food\_Name = (string)tbl.Rows\[i\]\["Food\_Name"\],  
FoodCategory\_ID = (string)tbl.Rows\[i\]\["FoodCategory\_ID"\],  
Price = (decimal)tbl.Rows\[i\]\["Price"\]  
});  
}  
[/csharp]

之後找到另一個方法  
就是用**LINQ**了

**解決方法**  
**C#**

[csharp]  
ShareChiWai\_Model Share\_ChiWai = new ShareChiWai_Model();  
DataTable tbl = Share\_ChiWai.Get\_Food_Tbl();

List<Food> Food_List = new List<Food>();  
Food_List = (from l in tbl.AsEnumerable() /\* Assume Linq to SQL \*/  
select new Food() { Food\_ID = l.Field<string>("Food\_ID"),  
Food\_Name = l.Field<string>("Food\_Name"),  
FoodCategory\_ID = l.Field<string>("FoodCategory\_ID"),  
Price = l.Field<decimal>("Price")

}).ToList<Food>();  
[/csharp]

Hope you find it useful