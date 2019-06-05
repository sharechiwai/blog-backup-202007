---
id: 1956
title: 'ASP.Net MVC DropDownList SelectedIndexChanged 一些ASP.Net MVC的很有用的Javascript I &#8211; 在ASP.Net MVC上的一個和ASP.Net DropDownList 的 SelectedIndexChanged 功能'
date: 2011-08-05T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1956
permalink: '/2011/08/asp-net-mvc-dropdownlist-selectedindexchanged-%e4%b8%80%e4%ba%9basp-net-mvc%e7%9a%84%e5%be%88%e6%9c%89%e7%94%a8%e7%9a%84javascript-i-%e5%9c%a8asp-net-mvc%e4%b8%8a%e7%9a%84%e4%b8%80%e5%80%8b%e5%92%8c/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC Drop Down List
  - ASP.Net Web Application To ASP.Net MVC 新手筆記
---
很多時候我們的**Web Application** 都會有一對對的**DropDownList**  
[讓使用者便可以**選擇產品編號 或 產品名稱**]  
當更變了其中一個**DropDownList**的值後..  
另一個**DropDownList** 的值都應該要相對地自動更變..  
在**ASP.Net Application**上我們可以透過使用**PostBack** 和 **Code Behind**  
來實現這個效果  
**.aspx**

<pre>&lt;h2&gt;
        Welcome to Share ChiWai ASP.NET!
    &lt;/h2&gt;
    Food Category:
    &lt;asp:DropDownList ID="ddl_FoodCategoriesID" runat="server" AutoPostBack="true"
        onselectedindexchanged="ddl_FoodCategoriesID_SelectedIndexChanged" /&gt;
    &lt;asp:DropDownList ID="ddl_FoodCategoriesName" runat="server"
        AutoPostBack="true"
        onselectedindexchanged="ddl_FoodCategoriesName_SelectedIndexChanged"/&gt;</pre>

我們要設定 **ASP.Net**的**DropDownList control**上的**AutoPostBack**屬性定寫為**true**  
和定義了**SelectedIndexChanged**功能

在**Code Behind**  
**C#**

[csharp]  
protected void Page_Load(object sender, EventArgs e)  
{  
if (!IsPostBack)  
{  
ShareChiWai\_Model Share\_tbl = new ShareChiWai_Model();  
DataTable tbl = Share\_tbl.Get\_Food_Categories();  
ddl\_FoodCategoriesID.DataSource = Share\_tbl.Get\_Food\_Categories();  
ddl\_FoodCategoriesID.DataTextField = "FoodCategory\_ID";  
ddl\_FoodCategoriesID.DataValueField = "FoodCategory\_ID";  
ddl_FoodCategoriesID.DataBind();

ddl\_FoodCategoriesName.DataSource = Share\_tbl.Get\_Food\_Categories();  
ddl\_FoodCategoriesName.DataTextField = "FoodCategory\_Name";  
ddl\_FoodCategoriesName.DataValueField = "FoodCategory\_ID";  
ddl_FoodCategoriesName.DataBind();  
}  
}

protected void ddl\_FoodCategoriesID\_SelectedIndexChanged(object sender, EventArgs e)  
{  
ddl\_FoodCategoriesName.SelectedValue = ddl\_FoodCategoriesID.SelectedValue;  
}

protected void ddl\_FoodCategoriesName\_SelectedIndexChanged(object sender, EventArgs e)  
{  
ddl\_FoodCategoriesID.SelectedValue = ddl\_FoodCategoriesName.SelectedValue;  
}  
[/csharp]

在另一個**DropDownList** 的**Selected Value** 設定為和這個**DropDownList**的**SelectedValue**  
一樣便可

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d7566d26d9ea448d8f3bc5cea2212535/renditions/fullsize.jpg?resize=452%2C228" alt="ASP.Net DropDownList SelectedIndexChanged Sample" width="452" height="228" data-recalc-dims="1" />  
在**ASP.Net MVC上..由於沒有ViewState** 和 每一個動作都不像**ASP.Net**一樣可以使用到**PostBack**的關係..  
所以在**ASP.Net MVC**上 我們會需要用到**Javascript**來實現這個效果..  
由於當建立**ASP.Net MVC 3 Projec**t時  
預設的**Project Template**已經把**JQuery**加進了Project上..和已然在**_Layout.cshtml**上引用了**Jquery**的參考..  
所以我可以使用**JQuery** 來寫一些**Javascript** 來實現這個樣果

.cshtml

[csharp]  
@{  
ViewBag.Title = "FoodCategories";  
}  
@model List<ShareChiWaiWebTutorial.Models.FoodCategory>  
@{  
//定義DropDownList內容  
var ddl\_FoodCategoriesID = new SelectList(Model, "FoodCategory\_ID", "FoodCategory_ID");  
var ddl\_FoodCategoriesName = new SelectList(Model, "FoodCategory\_ID", "FoodCategory_Name");  
}

<h2>Welcome To Share ChiWai ASP.Net MVC</h2>  
Food Categories:  
@Html.DropDownList("ddl\_FoodCategoriesID", ddl\_FoodCategoriesID)  
@Html.DropDownList("ddl\_FoodCategoriesName", ddl\_FoodCategoriesName)  
[/csharp]

[javascript]  
<script type="text/javascript">  
//當文件Ready的時候  
$(document).ready(function () {

DDL\_SelectedIndexChanged(&#8216;#ddl\_FoodCategoriesID&#8217;, &#8216;#ddl_FoodCategoriesName&#8217;);  
DDL\_SelectedIndexChanged(&#8216;#ddl\_FoodCategoriesName&#8217;, &#8216;#ddl_FoodCategoriesID&#8217;);  
});  
function DDL_SelectedIndexChanged(DDL1, DDL2) {  
//當DDL有改變時  
$(DDL1).change(function () {  
//DDL2的值會設定為DDL的值  
$(DDL2).val(this.value);  
});  
}

</script>;</pre>  
[/javascript]

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4c197fe1622b4ae6b72076f03d436d9b/renditions/fullsize.jpg?resize=608%2C324" alt="ASP.Net MVC DropDownList SelectedIndexChanged sample" width="608" height="324" data-recalc-dims="1" />  
這一次雖然**ASP.Net** 的程式碼比較簡短和方便&#8230;  
但是**ASP.Net MVC** 給使用者的感覺更流暢

Hope you find it useful