---
id: 2476
title: Convert DataTable/ DataColumn to List Of String
date: 2012-05-13T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2476
permalink: /2012/05/convert-datatable-datacolumn-to-list-of-string/
categories:
  - .Net Tips And Tricks
tags:
  - Convert DataTable to List Of Object
---
今天的其中一個Task 就是要令到之前寫的程式更加User-friendly  
這是我最差的地方&#8230;  
所以還是做一些簡單的**Message PopUp Box** 去提示使用者一些重要的資訊  
有時間的話才好好的安排怎樣Layout這個Application

我要把**DataTable** 上的其中一個**Column** 轉換成一段字..放便方在MessageBox上  
所以便在看怎樣可以實行了  
之前嘗試過把**List Of String** 轉換成 一段的String..  
[最壞打算是使用**For Loop**來**Loop**整個**DataTable**]

做了一段Research之後發現&#8230;解決方法十分簡單

**解決方法**:  
我做可以使用**LINQ** 人取得**DataRow**之後再取得這個DataColumn的值  
之後再把他轉成**List of String**

[vb]  
&#8216;以下是方便自己的一個功能&#8230;  
&#8216;大家需要轉入DataTable和 想Extract 的DataColumn名  
Public Function ConvertDataColumnToListOfString(ByVal tbl As DataTable, ByVal ColumnName As String) As List(Of String)  
&#8216;首先把Extract DataRow from DataTable  
Return (From dr As DataRow In tbl.Rows  
Select Convert.ToString(dr(ColumnName))).ToList() &#8216;之後想取出想要的DataColumn名

End Function  
[/vb]

Hope you find it useful