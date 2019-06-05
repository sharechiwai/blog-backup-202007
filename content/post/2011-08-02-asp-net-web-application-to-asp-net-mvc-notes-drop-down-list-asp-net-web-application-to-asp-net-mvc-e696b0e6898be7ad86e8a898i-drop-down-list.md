---
id: 1934
title: 'ASP.Net Web Application To ASP.Net MVC Notes Drop Down List- ASP.Net Web Application To ASP.Net MVC 新手筆記I Drop Down List'
date: 2011-08-02T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1934
permalink: '/2011/08/asp-net-web-application-to-asp-net-mvc-notes-drop-down-list-asp-net-web-application-to-asp-net-mvc-%e6%96%b0%e6%89%8b%e7%ad%86%e8%a8%98i-drop-down-list/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC Drop Down List
  - ASP.Net VS ASP.Net MVC3
  - ASP.Net Web Application To ASP.Net MVC 新手筆記
---
很多時候我們都會用到**Drop Down List** 的  
特別是當我們想給使用者選擇 的時候 [和你有很多資料要給用戶選擇其中一個資料的時候]  
為了方便大家對比**ASP.Net Web Application 和 ASP.Net MVC3 Web Application 有什麼不同**  
我希望在將來的網誌上做一些例子給大家參考

由於之前寫的**ASP.Net Web Application** 是使用 **ASP.Net Control** 的  
很方便..便可以建立一個**Drop Down List** 了  
E.G.  
**.aspx**

[csharp]  
<asp:DropDownList ID="ddl_FoodCategories" runat="server" />  
[/csharp]

**Code Behind**  
**C#**  
//這是一個簡單的**ASP.NET Drop Down List Sample**

[csharp]  
public partial class _Default : System.Web.UI.Page  
{  
//在Page Load Event上加入我們的Code  
protected void Page_Load(object sender, EventArgs e)  
{  
//當動作不是PostBack時我們取資料之後作Data Binding  
if (!IsPostBack)  
{  
//首先建立一個ShareChiWai_Model的 Instance  
ShareChiWai\_Model Share\_tbl = new ShareChiWai_Model();  
//用Get\_Food\_Categories()這個方法來取出一個Food Categories 的DataTable  
ddl\_FoodCategories.DataSource = Share\_tbl.Get\_Food\_Categories();  
//設定在Drop Down List上顯示的字為 "FoodCategory_Name" Field上的內容  
ddl\_FoodCategories.DataTextField = "FoodCategory\_Name";  
//設定當選擇Drop Down List時取的的內容為 "FoodCategory_NameID" Field上的內容  
ddl\_FoodCategories.DataValueField = "FoodCategory\_ID";  
//設定完成後進行Data Bind, 這便大功告成了  
ddl_FoodCategories.DataBind();  
}  
}  
}  
[/csharp]

<img title="ASP.Net Drop Down List Sample" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d317c63232bb47839cb6caab73d8e636/renditions/fullsize.jpg?resize=401%2C264" alt="ASP.Net Drop Down List Sample" width="401" height="264" data-recalc-dims="1" />  
而在A**SP.Net MVC**..由於我們不可以直接**DataBind**一個**DataTable**去一個**DropDownList Control**上..  
所以如果我們是使用**DataTable**的話便要自行把這個DataTable 轉成 List 才可以  
詳情可以參考以下URL:  
 <a title="Convert DataRow Array to DataTable, DataTable Filter function DataTable.Select return DataTable" href="http://blog.sharechiwai.com/2011/07/convert-datarow-array-to-datatable-datatable-filter-function-datatable-select-return-datatable/" target="_blank">Convert DataTable to List of Object – 把DataTable轉成List Of Object</a>  
我們先在Model上加入一個新的功能 來轉換 Get\_Food\_Categories方法取得的DataTable 轉為 List

**Model  
C#**

[csharp]  
public List<FoodCategory> Get\_Food\_Categories_List()  
{  
List<FoodCategory> Categories_List = new List<FoodCategory>();  
DataTable tbl = Get\_Food\_Categories();

for (int i = 0; i < tbl.Rows.Count; i++)  
{  
Categories_List.Add(new FoodCategory()  
{  
FoodCategory\_ID = (string)tbl.Rows\[i\]\["FoodCategory\_ID"\],  
FoodCategory\_Name = (string)tbl.Rows\[i\]\["FoodCategory\_Name"\]

});  
}  
return Categories_List;

}  
[/csharp]

把**Model** 建立好之後我們便可以把這個**Model pass去我們的 view上**面  
我們先在**Controller**上建立一個新的**Method FoodCategory**  
**Controller  
**C#****

[csharp]  
public ActionResult FoodCategories()  
{  
ViewBag.Message = "Show Food Categories";

ShareChiWai\_Model Share\_Model = new ShareChiWai_Model();

return View(Share\_Model.Get\_Food\_Categories\_List());  
}  
[/csharp]

之後我們便可以在我們的前台使用程式碼 建立我們的Drop Down List 了

**.cshtml  
View  
**C#** **

[csharp]  
//我們要在.cshtml上定義我們使用的Model是那一個什麼類型的東西  
@model List<ShareChiWaiWebTutorial.Models.FoodCategory>  
@{  
//建立一個SelectList的 Object 之後我們便可以 定義個Object了  
//new SelectList(“IEnumerable Item”, "DataValueField", "DataTextField");  
var ddl\_FoodCategories = new SelectList(Model, "FoodCategory\_ID", "FoodCategory_Name");  
}

<h2>FoodCategories</h2>  
//最後我們可以使手 Razor 把這個DropDownList Render出來了  
//@Html.DropDownList("Drop Down List的名稱/給Javascript/css 用的 E.G. 就像 ID 一樣", "SeletList Object")  
@Html.DropDownList("ddl\_FoodCategories", ddl\_FoodCategories)  
[/csharp]

<img title="ASP.Net MVC Drop Down List Sample" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cd333a7f9ecc46bf8278b871cd8a29cf/renditions/fullsize.jpg?resize=583%2C309" alt="ASP.Net MVC DropDownList Sample" width="583" height="309" data-recalc-dims="1" />  
**ASP.Net MVC**相比起 **ASP.Net** 要寫多很多程式嗎&#8230;  
當你嘗試多一點時..便會知道那一個比較適合你的Project使用的

Hope you find it useful

待續..