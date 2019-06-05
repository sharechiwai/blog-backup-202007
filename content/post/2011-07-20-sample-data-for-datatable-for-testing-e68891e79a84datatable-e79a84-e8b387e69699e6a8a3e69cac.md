---
id: 1896
title: 'Sample data for DataTable for testing &#8211; 我的DataTable 的 資料樣本'
date: 2011-07-20T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1896
permalink: '/2011/07/sample-data-for-datatable-for-testing-%e6%88%91%e7%9a%84datatable-%e7%9a%84-%e8%b3%87%e6%96%99%e6%a8%a3%e6%9c%ac/'
categories:
  - .Net Tips And Tricks
tags:
  - Dummy Sample Data
---
為了方便自己測候和示範一些**ASP.Net MVC/ ASP.Net/ WinForm/WPF/WCF 功能**  
我終於寫了一2個簡單的**Classes** 和一些Code 去建立一個 **Dummy 的DataTable/DataSet,**和一些小小的功能幫助取資料

第一個**Class** 是**Food Category 用來把食物分類的**  
**C#**

[csharp]  
public class FoodCategory  
{  
public string FoodCategory_ID {get;set;}  
public string FoodCategory_Name {get;set;}  
}  
[/csharp]

另一個**Class** 是**食物 來定義食的名**和那一個類等等

C#

[csharp]  
public class Food  
{  
public string Food_ID { get; set; }  
public string Food_Name { get; set; }  
public decimal Price { get; set; }  
public string FoodCategory_ID{get;set;}  
}  
[/csharp]

之後我便定義了一個**Helper Class**  
用來方便自己取資料的  
由於最終的目的是用來**simulate** 連接**database** 後  
最出資料到**DataTable**上的動作..  
[因為我常常感到..當我要測試一些資料時  
需要連接到資料庫取資料是一件得麻煩的是..  
因為在電腦上我沒有自己啟用**MSSQL Server**的  
還有.即使連接了**SQL Server**  
我們還是要寫一些**SQL** 來取資料..  
所以便有了這個想法去建立一個有**小小Relational 的Dummy DataTable**了]

以下是我所建立的**Helper class** 的所有的程式碼  
**C#**

[csharp]  
public class ShareChiWai_Model  
{  
//這可以取得所有Food的資料放在DataTable上  
public DataTable Get\_Food\_Tbl()  
{  
DataTable tbl = new DataTable();  
tbl.Columns.Add(new DataColumn("Food_ID", Type.GetType("System.String")));  
tbl.Columns.Add(new DataColumn("Food_Name", Type.GetType("System.String")));  
tbl.Columns.Add(new DataColumn("Price", Type.GetType("System.Decimal")));  
tbl.Columns.Add(new DataColumn("FoodCategory_ID", Type.GetType("System.String")));

DataRow dr1 = tbl.NewRow();  
dr1["Food_ID"] = "00001";  
dr1["Food_Name"] = "Apple";  
dr1["Price"] = 0.99;  
dr1["FoodCategory_ID"] = "00001";  
tbl.Rows.Add(dr1);

DataRow dr2 = tbl.NewRow();  
dr2["Food_ID"] = "00002";  
dr2["Food_Name"] = "American bison";  
dr2["Price"] = 7.99;  
dr2["FoodCategory_ID"] = "00002";  
tbl.Rows.Add(dr2);

tbl.Rows.Add(new Object[] { "00003", "Asparagus", 3.99, "00003" });  
tbl.Rows.Add(new Object[] { "00004", "Banana", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00005", "Beef", 1.99, "00002" });  
tbl.Rows.Add(new Object[] { "00006", "Broccoli", 1.09, "00003" });  
tbl.Rows.Add(new Object[] { "00007", "Cherry", 1.99, "00001" });  
//start Vegetable  
tbl.Rows.Add(new Object[] { "00008", "Yams", 1.99, "00003" });  
tbl.Rows.Add(new Object[] { "00009", "Sweet potatoes", 5.99, "00003" });  
tbl.Rows.Add(new Object[] { "00010", "Olives", 5.99, "00003" });  
tbl.Rows.Add(new Object[] { "00011", "Tomato", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00012", "Spinach", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00013", "Radish", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00014", "Pumpkin", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00015", "Onion", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00016", "Nopales ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00017", "Mushrooms ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00018", "Leeks ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00019", "Kohlrabi ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00020", "Japanese Eggplant ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00021", "Hot Pepper", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00022", "Garlic", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00023", "Fordhooks ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00024", "Eggplant ", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00025", "Dinosaur Kale", 0.99, "00003" });  
tbl.Rows.Add(new Object[] { "00026", "Cabbage ", 0.99, "00003" });  
//End Vegetable  
tbl.Rows.Add(new Object[] { "00027", "Cattle", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00028", "Duck", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00029", "E &#8212; Unknown", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00030", "Fugu", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00031", "Guinea pig", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00032", "Zebra", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00033", "Whale", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00034", "Tuna", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00035", "Salmon", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00036", "Pork", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00037", "Orange Roughy", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00038", "Milkfish", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00039", "Kingfish", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00040", "Watermelon", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00041", "Strawberries", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00042", "Raspberries", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00043", "Raisins", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00044", "Prunes", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00045", "Plums", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00046", "Haddock", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00047", "Nutria", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00048", "Lamb", 0.99, "00002" });  
tbl.Rows.Add(new Object[] { "00049", "Iguana", 0.99, "00002" });

//fruit continue  
tbl.Rows.Add(new Object[] { "00050", "Orange", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00051", "Mango", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00052", "Kiwi", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00053", "Lime", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00054", "Jackfruit", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00055", "Guava", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00056", "Grapefruit", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00057", "Fig", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00058", "Durian", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00059", "Papaya", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00060", "Ugli Fruit", 0.99, "00001" });  
tbl.Rows.Add(new Object[] { "00061", "Tamarillo", 0.99, "00001" });  
//Fruit End

return tbl;  
}

//這可以取得Food Categories 的資料放在DataTable上  
public DataTable Get\_Food\_Categories()  
{  
DataTable tbl = new DataTable();  
tbl.Columns.Add(new DataColumn("FoodCategory_ID", Type.GetType("System.String")));  
tbl.Columns.Add(new DataColumn("FoodCategory_Name", Type.GetType("System.String")));

DataRow dr1 = tbl.NewRow();  
dr1["FoodCategory_ID"] = "00001";  
dr1["FoodCategory_Name"] = "Fruit";  
tbl.Rows.Add(dr1);

DataRow dr2 = tbl.NewRow();  
dr2["FoodCategory_ID"] = "00002";  
dr2["FoodCategory_Name"] = "Meat/Animal";  
tbl.Rows.Add(dr2);  
DataRow dr3 = tbl.NewRow();  
dr3["FoodCategory_ID"] = "00003";  
dr3["FoodCategory_Name"] = "Vegetable";  
tbl.Rows.Add(dr3);

return tbl;  
}  
//這可以取得在指定的CategoryID資訊  
public DataTable Get\_CategoryByID(string FoodCategory\_ID)  
{

DataTable tbl = new DataTable();  
DataRow[] dr\_Array = Get\_Food\_Categories().Select("FoodCategory\_ID =&#8217;" + FoodCategory_ID + "&#8217;");  
if (dr_Array.Length > 0)  
{  
tbl = dr_Array[0].Table.Copy();  
tbl.Clear();  
}

foreach (DataRow dr in dr_Array)  
{  
tbl.ImportRow(dr);  
}  
return tbl;  
}  
//這可以取得在指定的CategoryID內的食物資料  
public DataTable Get\_FoodByCategoryID(string FoodCategory\_ID)  
{

DataTable tbl = new DataTable();  
DataRow[] dr\_Array =Get\_Food\_Tbl().Select("FoodCategory\_ID =&#8217;" + FoodCategory_ID + "&#8217;");  
if (dr_Array.Length > 0)  
{  
tbl = dr_Array[0].Table.Copy();  
tbl.Clear();  
}

foreach (DataRow dr in dr_Array)  
{  
tbl.ImportRow(dr);  
}  
return tbl;  
}

//這可以取得在指定的食物資料  
public DataTable Get\_FoodByID(string Food\_ID)  
{

DataTable tbl = new DataTable();  
DataRow[] dr\_Array = Get\_Food\_Tbl().Select("Food\_ID =&#8217;" + Food_ID + "&#8217;");  
if (dr_Array.Length > 0)  
{  
tbl = dr_Array[0].Table.Copy();  
tbl.Clear();  
}

foreach (DataRow dr in dr_Array)  
{  
tbl.ImportRow(dr);  
}  
return tbl;  
}  
}  
//Food Category Class  
public class FoodCategory  
{  
public string FoodCategory_ID { get; set; }  
public string FoodCategory_Name { get; set; }  
}  
//Food Class  
public class Food  
{  
public string Food_ID { get; set; }  
public string Food_Name { get; set; }  
public decimal Price { get; set; }  
public string FoodCategory_ID { get; set; }  
}  
[/csharp]  
之後我們便可以運用個Helper class 來取得一些我們可以用的測試資料了  
E.G.  
[csharp]  
ShareChiWai\_Model Share\_ChiWai = new ShareChiWai_Model();  
DataTable tbl\_FoodCategories = Share\_ChiWai.Get\_Food\_Categories(); //這可以取得Food Categories 的資料放在DataTable上  
[/csharp]

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/156d9242fe644206aa17557571df43cb/renditions/fullsize.jpg?resize=515%2C214" alt="" width="515" height="214" data-recalc-dims="1" /> 

[csharp]  
DataTable tbl\_Foods = Share\_ChiWai.Get\_Food\_Tbl();//這可以取得所有Food的資料放在DataTable上  
[/csharp]

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7f96f1bda6b844bd819327f98b012b50/renditions/fullsize.jpg?resize=519%2C387" alt="" width="519" height="387" data-recalc-dims="1" /> 

[csharp]  
DataTable tbl\_CategoryByID =Share\_ChiWai.Get_CategoryByID("00001"); //這可以取得在指定的CategoryID資訊  
[/csharp]

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/85042dadb30648c7a62441b26deef5dd/renditions/fullsize.jpg?resize=520%2C196" alt="" width="520" height="196" data-recalc-dims="1" /> 

[csharp]  
DataTable tbl\_FoodByID =Share\_ChiWai.Get_FoodByID("00008");//這可以取得在指定的食物資料  
[/csharp]

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/264bbc3d7e1f45ebb25c6a8710879662/renditions/fullsize.jpg?resize=524%2C186" alt="" width="524" height="186" data-recalc-dims="1" /> 

[csharp]  
DataTable tbl\_FoodByCategoryID =Share\_ChiWai.Get_FoodByCategoryID("00001"); //這可以取得在指定的CategoryID內的食物資料  
[/csharp]

<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a96d67db9cd54b10a7b91782566103ce/renditions/fullsize.jpg?resize=514%2C390" alt="" width="514" height="390" data-recalc-dims="1" />  
將來再次加入更多的有用功能

Hope you find it useful