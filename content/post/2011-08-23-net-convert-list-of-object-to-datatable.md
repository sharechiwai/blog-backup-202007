---
id: 1997
title: .Net Convert List of Object To DataTable
date: 2011-08-23T00:00:41+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1997
permalink: /2011/08/net-convert-list-of-object-to-datatable/
categories:
  - .Net Tips And Tricks
tags:
  - ASP.Net MVC
  - Convert List Of Object To DataTable
  - List Of Object 轉換成 DataTable
---
今天其中一個Task 是要建立一個**Export Data to XLSX 或 CSV** 的功能..  
由於大部分在**ASP.Net MVC**的 Code中 做**DataBind 時要使用到List Of Object**的關係  
所以我很多的功能 的 輸出/return 類型都是使用**List Of Object** 的

由於希望用來**Export** 資料的功能能夠 把所有輪入的資料 E.G. **List Of Object** 入的 所有屬性 都會輸出來的關係

而自己又不太了解怎樣可以 在一個**Object 上 移除一些不想要的屬性**..  
最後我決定嘗試寫一個方法把 **List Of Object 轉換成 DataTable  
<span class="Apple-style-span" style="font-weight: 300;"><br /> 有趣的是之前寫這一個Post是關於 <a title="Permalink to Convert DataTable to List of Object – 把DataTable轉成List Of Object" href="http://blog.sharechiwai.com/2011/07/convert-datatable-to-list-of-object-%e6%8a%8adatatable%e8%bd%89%e6%88%90list-of-object/" rel="bookmark">Convert DataTable to List of Object – 把DataTable轉成List Of Object</a> 而今次是做相反的事</span>**

以下是這個功能:

**解決方法:**  
**C#**

[csharp]  
//這個方法用了Generic Type..因為這樣我們可建立一個method..這個Method 沒有注定要用那一個類的  
//我們的 Parameter 會是 IList //generic Type  
public DataTable ConvertListObjectToDataTable(IList ListOfData)  
{  
//使用 TypeDescriptor 的GetProperties 方法 取得這個 List 的類別..的所有屬性  
PropertyDescriptorCollection ObjectPropertyArray = TypeDescriptor.GetProperties(typeof(T));  
//建立一個DataTable  
DataTable tbl = new DataTable();  
之後我們可以用For Loop來 Loop through 用GetProperties 取出的屬性  
for (int i = 0; i < ObjectPropertyArray.Count; i++)  
{  
//建立Table 的 Column  
//我們可以用 PrepertyDescriptor的 Name 來取得 屬性的名稱  
//用PropertyType的屬性 來取出 屬性的DataType  
//之後用 Nullable.GetUnderlyingType 把Nullable 的 DataType 轉成 DataTable的DataType  
tbl.Columns.Add(new DataColumn(ObjectPropertyArray[i].Name, Nullable.GetUnderlyingType(ObjectPropertyArray[i].PropertyType) ?? ObjectPropertyArray[i].PropertyType));  
}

//建立一個Object Array用來把List Of Object的資料加在一起  
object[] Obj = new object[ObjectPropertyArray.Count];  
//用For Loop 去Loop through List Of Object 的每一個Item  
for (int i = 0; i < ListOfData.Count; i++)  
{  
//用 For Loop 把 每一個Item的 屬性 加進 Object Array 上  
for (int j = 0; j < ObjectPropertyArray.Count; j++)  
{

Obj[j] = ObjectPropertyArray[j].GetValue(ListOfData[i]);  
}  
//把Object Array 加進DataTable 上  
tbl.Rows.Add(Obj);  
}  
//Return Data Table  
return tbl;  
}  
[/csharp]

**VB**  
[vb]  
Public Function ConvertListObjectToDataTable(Of T)(ListOfData As IList) As DataTable  
Dim ObjectPropertyArray As PropertyDescriptorCollection = TypeDescriptor.GetProperties(GetType(T))  
Dim tbl As New DataTable()

For i As Integer = 0 To ObjectPropertyArray.Count &#8211; 1  
tbl.Columns.Add(New DataColumn(ObjectPropertyArray(i).Name, If(Nullable.GetUnderlyingType(ObjectPropertyArray(i).PropertyType), ObjectPropertyArray(i).PropertyType)))  
Next  
Dim Obj As Object() = New Object(ObjectPropertyArray.Count &#8211; 1) {}  
For i As Integer = 0 To ListOfData.Count &#8211; 1

For j As Integer = 0 To ObjectPropertyArray.Count &#8211; 1  
Obj(j) = ObjectPropertyArray(j).GetValue(ListOfData(i))  
Next  
tbl.Rows.Add(Obj)  
Next  
Return tbl  
End Function  
[/vb]  
**Sample Code:**  
**C#**

[csharp]  
//建立一個ShareChiWai_Model 用來取Sample Data  
ShareChiWai\_Model Share\_Model = new ShareChiWai_Model();  
//用Get\_Food\_List 來取出 List Of Food item  
List Food\_List = Share\_Model.Get\_Food\_List();  
//加入一個Empty Object 用來測試 這個功能對 Null Value的反應  
Food\_List.Insert(2, new Food(){Food\_ID= null, Food_Name=null});  
//Convert List Of Object To DataTable  
DataTable tbl = ConvertListObjectToDataTable(Food_List);  
[/csharp]

Hope you find it useful