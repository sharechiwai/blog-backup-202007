---
id: 2001
title: 'ASP.Net Web Application To ASP.Net MVC Notes II Drop Down List Sorting DropDownList- ASP.Net Web Application To ASP.Net MVC 新手筆記II Drop Down List 排序'
date: 2011-08-25T00:00:40+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2001
permalink: '/2011/08/asp-net-web-application-to-asp-net-mvc-notes-ii-drop-down-list-sorting-dropdownlist-asp-net-web-application-to-asp-net-mvc-%e6%96%b0%e6%89%8b%e7%ad%86%e8%a8%98ii-drop-down-list-%e6%8e%92%e5%ba%8f/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC Drop Down List
  - ASP.Net Web Application To ASP.Net MVC 新手筆記
  - DataTable
  - LINQ
  - Sorting DataTable
---
在之前的 Post介紹了**如何在ASP.Net MVC 上建立DropDownList**

<a title="ASP.Net Web Application To ASP.Net MVC Notes Drop Down List- ASP.Net Web Application To ASP.Net MVC 新手筆記I Drop Down List" href="http://blog.sharechiwai.com/2011/08/asp-net-web-application-to-asp-net-mvc-notes-drop-down-list-asp-net-web-application-to-asp-net-mvc-%e6%96%b0%e6%89%8b%e7%ad%86%e8%a8%98i-drop-down-list/" target="_blank">ASP.Net Web Application To ASP.Net MVC Notes Drop Down List- ASP.Net Web Application To ASP.Net MVC 新手筆記I Drop Down List</a>

和在這個Post 上介紹了**如何在 ASP.Net MVC 上如何實現SelectedIndexChanged 的效果**  
 <a title="ASP.Net MVC DropDownList SelectedIndexChanged 一些ASP.Net MVC的很有用的Javascript I – 在ASP.Net MVC上的一個和ASP.Net DropDownList 的 SelectedIndexChanged 功能" href="http://blog.sharechiwai.com/2011/08/asp-net-mvc-dropdownlist-selectedindexchanged-%e4%b8%80%e4%ba%9basp-net-mvc%e7%9a%84%e5%be%88%e6%9c%89%e7%94%a8%e7%9a%84javascript-i-%e5%9c%a8asp-net-mvc%e4%b8%8a%e7%9a%84%e4%b8%80%e5%80%8b%e5%92%8c/" target="_blank">ASP.Net MVC DropDownList SelectedIndexChanged 一些ASP.Net MVC的很有用的Javascript I – 在ASP.Net MVC上的一個和ASP.Net DropDownList 的 SelectedIndexChanged 功能</a>

現在發現有些美中不足的地方..  
就是當我們有一對**DropDownList** &#8230;  
一個是用來給用戶以產品 ID 來選擇 的  
另一個是用產品名稱給用戶選擇&#8230;  
由於資料是在資料庫取出來的..  
如果我們在資訊庫的排序 是以  
**產品編號 或產品名稱 來排序的&#8230; 另一面便有可能不會順序了**  
[因為資料輸入的次序可能不一樣.. 和 **產品編號 / 編號 多數是用 Auto ID產生 的**]  
如果我們直接把資料databind 鎖定到**DropDownList**上&#8230; 當使用者選擇/使用**DropDownList** 便可能會感覺到怪怪的了.. 因為資料可能不是順序的  
**以Food ID來排序**  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/113ec8e22bb9425ea0d187fe64e1d2f4/renditions/fullsize.jpg?resize=447%2C303" alt="ASP.Net MVC DropDownList Sorted By Food ID" width="447" height="303" data-recalc-dims="1" /> 

**可惜 Food Name 沒有被排序**  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d08bb4715c3d46d1b235ae358b59f8a9/renditions/fullsize.jpg?resize=500%2C316" alt="ASP.Net MVC DropDownList Unsorted" width="500" height="316" data-recalc-dims="1" />  
**解決方法:**  
**1)** 使用2個不同的Query 來取後資料&#8230; 一個以產品編號來排序 而別一個以產品名稱 來排序  
[這個方法會佔了資料庫的資源..感覺不太好.. E.G. 當你有一個比較複雜的 Query是 便會感到他的問題]

**2)** 另一個方法是在取得到給果後 在**List Of <Object> 上 或DataTable上進行排序**  
[感覺好一點]

**以下是程式碼**  
**ASP.Net** 時代.. 我使用**DataTable** 是這樣解決的|  
**.aspx &#8211;這裡我們有一對DropDownList**

<pre>&lt;h2&gt;
        Welcome to Share ChiWai ASP.NET!
    &lt;/h2&gt;
    Food: &lt;asp:DropDownList ID="ddl_Food" runat="server" /&gt;
    &lt;asp:DropDownList ID="ddl_Food_Name" runat="server" /&gt;</pre>

**c#**

[csharp]  
//這個Sample 我們在Page_Load Event上 做DataBind  
protected void Page_Load(object sender, EventArgs e)  
{  
if (!IsPostBack)  
{  
//使用 ShareChiWai\_Model上的 Get\_FoodByCategoryID 來取出一些 食物名稱  
ShareChiWaiWebTutorial.Models.ShareChiWai\_Model Share\_Model = new ShareChiWaiWebTutorial.Models.ShareChiWai_Model();  
//之後Assign 到DataTable上 以便可以Assign 到2個DropDownList 的DataSource上  
DataTable tbl\_Food = Share\_Model.Get_FoodByCategoryID("00003");  
//假設我們的Data已經以 Food_ID來排序  
//所以我們可以直接把他Assign到 DropDownList的DataSource上  
ddl\_Food.DataSource = tbl\_Food;  
ddl\_Food.DataTextField = "Food\_ID";  
ddl\_Food.DataValueField = "Food\_ID";  
ddl_Food.DataBind();  
//為了令到我們的DropDownList更可用. 我們需要幫Food_Name 這一個DropDownList 排序  
//由於我們是使DataTable的關係..所以我們可以用 DataTable.DefaultView.Sort ="要排序的 Column 名稱"  
//這便可以把這個DataTable排序了  
tbl\_Food.DefaultView.Sort = "Food\_Name";  
//之後再幫DataTable Assign到另一個DropDownList上便完成了  
ddl\_Food\_Name.DataSource = tbl_Food;  
ddl\_Food\_Name.DataTextField = "Food_Name";  
ddl\_Food\_Name.DataValueField = "Food_ID";  
ddl\_Food\_Name.DataBind();

}  
}  
[/csharp]

**Asp.Net 結果**  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/113ec8e22bb9425ea0d187fe64e1d2f4/renditions/fullsize.jpg?resize=447%2C303" alt="ASP.Net Drop Down List Sorted" width="447" height="303" data-recalc-dims="1" />  
**ASP.Net MVC**  
**.Controller**  
**C#**

[csharp]  
//建立一個 ShareChiWai_Model 用來取資料用的  
private ShareChiWai\_Model Share\_Model;  
public DropDownListSortingController()  
{  
Share\_Model = new ShareChiWai\_Model();  
}

public ActionResult Index()  
{  
//使用 ShareChiWai\_Model上的 Get\_FoodByCategoryID_List 來取出一些 食物名稱  
List Food\_List = Share\_Model.Get\_FoodByCategoryID\_List("00003");  
//之後Pass到我們的View 上  
return View(Food_List);  
}  
[/csharp]

**.cshtml**

<pre>&lt;h2&gt;Drop Down List Sorting&lt;/h2&gt;
//定義了這一個頁用的Model 是 List Of Food 的類的
@model List&lt;ShareChiWaiWebTutorial.Models.Food&gt;
@{
//把 List Of Food DataBind 到 SelectList 上 for Food_ID 用的DropDownList
    var ddl_Food = new SelectList(Model, "Food_ID", "Food_ID");
//用Variable來 儲存 Food_ID 以方便 把SelectedValue Assign到下一個DropDownList上
//令到資料更Consistant
string SelectedFoodID= Model[0].Food_ID;
//之後我們會做差不多的動作 For Food Name 用的DropDownList
//為一分別是 我們要重新排列 這一個List..以Food Name來排序
//我們可以使用LINQ 的放法 去解決這個問題..
<span style="font-family: 'Courier 10 Pitch', Courier, monospace; font-size: x-small;"><span class="Apple-style-span" style="line-height: 19px;">// Model.OrderBy(f =&gt; f.要排序的屬性).ToList() </span></span>var ddl_FoodName = new SelectList(Model.OrderBy(f =&gt; f.Food_Name).ToList() , "Food_ID", "Food_Name", SelectedFoodID);
 }

&lt;h2&gt;Food Categories&lt;/h2&gt;
Food:
@Html.DropDownList("ddl_Food", ddl_Food)
@Html.DropDownList("ddl_FoodName", ddl_FoodName)</pre>

**ASP.Net MVC DropDownList Sorted 成果**  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/46fed8470f784cad83974f33d075ef4a/renditions/fullsize.jpg?resize=478%2C324" alt="" name="" width="478" height="324" data-recalc-dims="1" />  
Hope you find it useful