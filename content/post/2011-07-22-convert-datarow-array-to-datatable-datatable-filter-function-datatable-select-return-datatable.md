---
id: 1911
title: Convert DataRow Array to DataTable, DataTable Filter function DataTable.Select return DataTable
date: 2011-07-22T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1911
permalink: /2011/07/convert-datarow-array-to-datatable-datatable-filter-function-datatable-select-return-datatable/
categories:
  - .Net Tips And Tricks
tags:
  - ASP.Net
  - ASP.Net MVC
  - DataTable
---
最近嘗試在建立**Dummy Data Class**的時候  
E.G. **嘗試建立一個Class 用來Return 一個DataTable**  
之後建立一些function 用來幫助**filter DataTable**上的資料的Class  
目的是在測試.或做**Demo**一些功能的時候 **不想連接到Database 和都想寫SQL Code**  
**C#**

[csharp]  
public DataTable Get\_FoodByCategoryID(string FoodCategory\_ID)  
{

DataTable tbl = new DataTable();  
//我們可以使用DataTable.Select 這個方法在DataTable上建立一個Filter [就像SQL中的Where Clause一樣]  
//得可惜DataTable.Select 只能夠return DataRow Array&#8230;  
DataRow[] dr\_Array = Get\_Food\_Tbl().Select("FoodCategory\_ID =&#8217;" + FoodCategory_ID + "&#8217;");

//所我們便要下一些功夫把 DataRow Array 轉成DataTable

if (dr_Array.Length > 0)  
{  
//由於在Import DataRow時 DataTable 不懂得自我更新DataTable的Structure的關係  
//所以我們便要複製一個 DataRow Array上的DataTable Structure了  
tbl = dr_Array[0].Table.Copy();  
//取後DataTable Structure 之後便要Clear這個DataTable的內容了  
tbl.Clear();  
}  
//之後我們便需要用For Each Loop 來把這個 DataRow Array入面的每一個Row 取出來  
foreach (DataRow dr in dr_Array)  
{  
之後使用 DataTable.ImportRow這個method來把Row import進DataTable 上  
tbl.ImportRow(dr);  
}  
//這樣便解決了, Convert DataRow Array to DataTable的問題  
return tbl;  
}  
[/csharp]

Hope you find it useful