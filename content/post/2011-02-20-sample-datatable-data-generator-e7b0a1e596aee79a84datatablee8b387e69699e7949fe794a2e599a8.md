---
id: 1663
title: 'Sample DataTable Data Generator &#8211; 簡單的DataTable資料生產器'
date: 2011-02-20T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1663
permalink: '/2011/02/sample-datatable-data-generator-%e7%b0%a1%e5%96%ae%e7%9a%84datatable%e8%b3%87%e6%96%99%e7%94%9f%e7%94%a2%e5%99%a8/'
categories:
  - .Net Tips And Tricks
---
今日想和大家分享一些程式碼..  
他們是我在測試時常常使用的&#8230;  
因為通常每當我在家裡想測試一些和**DataTable**有關的功能時  
E.G. **DataTable** to **DataGridView**, **GridView**, **Export to CSV**, **XLSX** 或其他有使用到**Data**的功能時  
我都會自己寫一個小小的**DataTable**出來方便自己的

最近寫了一個功能方便自己做這個動作&#8230;  
所以希望在這裡和大家分享..  
以方便大家測試和DataTable有關的功能

使用方法  
**VB.Net**

[vbnet]  
&#8216;這便會產生一個有10行資料的DataTable 出來的  
Dim tbl as DataTable = GenerateData(10)  
[/vbnet]

**C#**

[csharp]

//這便會產生一個有10行資料的DataTable 出來的  
DataTable tbl = GenerateData(10);  
[/csharp]

**VB.Net**

[vbnet]  
Public Function GenerateData(ByVal NoOfRecord As Integer) As DataTable  
Dim tbl As New DataTable  
tbl.Columns.Add(New DataColumn("ID", Type.GetType("System.Int32")))  
tbl.Columns.Add(New DataColumn("Food Name", Type.GetType("System.String")))  
tbl.Columns.Add(New DataColumn("Delivery Date", Type.GetType("System.DateTime")))  
tbl.Columns.Add(New DataColumn("Profit", Type.GetType("System.Decimal")))  
tbl.Columns.Add(New DataColumn("Available", Type.GetType("System.Boolean")))

Dim StringArray() As String = {"Apple", "Banana", "Cake", "Dim Sum", "Egg", "French Bread", "Ginger",  
"Halloumi cheese", "Ice-cream", "Jelly", "Kiwi fruit", "Lamb", "Moon cake",  
"Nachos", "Orange", "Peanet", "Quail&#8217;s egg", "Raisins", "Sea Salt",  
"Tea", "Vegetables", "Water", "Yoghurt", "Zest"}  
Dim rand As New Random

For i As Integer = 1 To NoOfRecord  
Dim dr As DataRow = tbl.NewRow  
dr("ID") = i  
dr("Food Name") = StringArray(rand.Next(StringArray.Count))  
dr("Delivery Date") = New Date(2010, 1, 1).AddDays(rand.Next(365))  
dr("Profit") = rand.NextDouble() * 100  
dr("Available") = IIf(rand.Next(2) = 1, True, False)  
tbl.Rows.Add(dr)  
Next

Return tbl  
End Function  
[/vbnet]

**C#**

[csharp]

public DataTable GenerateData(int NoOfRecord)  
{  
DataTable tbl = new DataTable();  
tbl.Columns.Add(new DataColumn("ID", Type.GetType("System.Int32")));  
tbl.Columns.Add(new DataColumn("Food Name", Type.GetType("System.String")));  
tbl.Columns.Add(new DataColumn("Delivery Date", Type.GetType("System.DateTime")));  
tbl.Columns.Add(new DataColumn("Profit", Type.GetType("System.Decimal")));  
tbl.Columns.Add(new DataColumn("Available", Type.GetType("System.Boolean")));

string[] StringArray = {  
"Apple",  
"Banana",  
"Cake",  
"Dim Sum",  
"Egg",  
"French Bread",  
"Ginger",  
"Halloumi cheese",  
"Ice-cream",  
"Jelly",  
"Kiwi fruit",  
"Lamb",  
"Moon cake",  
"Nachos",  
"Orange",  
"Peanet",  
"Quail&#8217;s egg",  
"Raisins",  
"Sea Salt",  
"Tea",  
"Vegetables",  
"Water",  
"Yoghurt",  
"Zest"  
};  
Random rand = new Random();

for (int i = 1; i <= NoOfRecord; i++) {  
DataRow dr = tbl.NewRow();  
dr["ID"] = i;  
dr["Food Name"] = StringArray[rand.Next(StringArray.Count)];  
dr["Delivery Date"] = new System.DateTime(2010, 1, 1).AddDays(rand.Next(365));  
dr["Profit"] = rand.NextDouble() * 100;  
dr["Available"] = (rand.Next(2) == 1 ? true : false);  
tbl.Rows.Add(dr);  
}

return tbl;  
}  
[/csharp]

Hope you find it useful