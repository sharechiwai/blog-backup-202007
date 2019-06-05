---
id: 2017
title: 'ASP.Net MVC Cascaded DropDownList &#8211; 在ASP.Net MVC 中實現級聯下拉框'
date: 2011-08-26T00:00:58+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2017
permalink: '/2011/08/asp-net-mvc-cascaded-dropdownlist-%e5%9c%a8asp-net-mvc-%e4%b8%ad%e5%af%a6%e7%8f%be%e7%b4%9a%e8%81%af%e4%b8%8b%e6%8b%89%e6%a1%86/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC
  - ASP.Net MVC Drop Down List
  - ASP.Net Web Application To ASP.Net MVC 新手筆記
  - Cascading Drop Down List
  - dropdownlist
---
在網頁上..很多時候都會出現一些**Cascaded DropDownList.**..  
主要是因為有一些資料..是要依賴之前選擇的資料..再從資料庫找出相關的資料..給客戶選擇的  
**例如:**  
**國家 和城市**&#8230;  
**年/月/日**等等&#8230;  
**E.G.**  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4dfb1867b608410bac52fa443464c377/renditions/fullsize.jpg?resize=576%2C270" alt="2 pairs of DropDownList represent Food Category and Food" width="576" height="270" data-recalc-dims="1" />  
在**ASP.Net** 上 可以很簡單地用 **DropDownList Auto-Postback** 的特性..  
今到使用者選擇了**DropDownList**的內容後做一個**PostBack**..  
使**Server**從新再**DataBind** 和他想關的**DropDownList**&#8230;  
很簡單便可以實現這個效果了  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f7c8dbc7f5374b1e97fd4b572efa6097/renditions/fullsize.jpg?resize=556%2C284" alt="dropdownlist without linking together" width="556" height="284" data-recalc-dims="1" /> 

在**ASP.Net MVC**&#8230;由於沒有**PostBack**這個特性的關係.. 我們便要做多一點功夫了  
**解決方法**:  
我們會用 **Food Category** 和 **Food** 的關係做這個示範的  
會用到**4個DropDownList**&#8230;  
給**Food Category ID**, **Food Category Name**, **Food ID**, **Food Name**  
**2對的DropDownList.**

每一個**Food** 都有一個**Food Category ID**&#8230;  
所以每當用戶更改 **Food Category** 這**一對DropDownList**之後  
下面的**Food DropDownList便會跟著更新**

我們會需要在**View** 上使用到**JQuery** 來做一個**Ajax Request** 取得 和**Food Category** 相關的**Food** 的資料的  
和在**Controller**上建立一個**return JSON 的 Action**  
**Model**  
**C#**

[csharp]  
//這是我為這個DropDownList 所建立的一個Model..  
//他有一個Food Category List和Food List 用來示範有Cascading Drop Down List的情況的  
public class FoodCategory\_SelectionOptions\_Model  
{  
public List FoodCategory_List { get; set; }  
public List Food_List { get; set; }  
}  
[/csharp]

**Controller**  
**C#**

[csharp]  
// 大至上和之前的POST 差不多..所以我也不多加註釋了  
private ShareChiWai\_Model Share\_Model;

public CascadingDropDownListController()  
{  
Share\_Model = new ShareChiWai\_Model();  
}

public ActionResult Index()  
{  
FoodCategory\_SelectionOptions\_Model MainModel = new FoodCategory\_SelectionOptions\_Model();  
List Category\_List = Share\_Model.Get\_Food\_Categories_List();  
MainModel.FoodCategory\_List = Category\_List;

if (Category_List.Count > 0)  
{  
MainModel.Food\_List = Share\_Model.Get\_FoodByCategoryID\_List(Category\_List[0].FoodCategory\_ID);  
}

return View(MainModel);  
}  
//這個功能用來把ShareChiWai\_Model的Get\_FoodByCategoryID_List的結果轉成JSON Result給我們的.cshtml 去把資料重新再Assign 到dropdownlist上  
public JsonResult SelectedFoodCategory(string Food\_Category\_ID)  
{  
List Food\_List = Share\_Model.Get\_FoodByCategoryID\_List(Food\_Category\_ID);  
//我們會用到 Json(Model,和 Request的方法)  
return Json(Food_List, JsonRequestBehavior.AllowGet);

}  
[/csharp]

**.cshtml**

<pre>//大至上和之前的POST 差不多.. 大家有什麼不明白或有更好的方法歡迎大家留言
@model ShareChiWaiWebTutorial.Models.FoodCategory_SelectionOptions_Model
@{
    var ddl_FoodCategories = new SelectList(Model.FoodCategory_List, "FoodCategory_ID", "FoodCategory_ID");
    string SelectedFoodCategory = Model.FoodCategory_List[0].FoodCategory_ID;
    var ddl_FoodCategoriesName = new SelectList(Model.FoodCategory_List.OrderBy(f=&gt;f.FoodCategory_Name), "FoodCategory_ID", "FoodCategory_Name", SelectedFoodCategory);

    var ddl_Food = new SelectList(Model.Food_List, "Food_ID", "Food_ID");
    string SelectedFood = Model.Food_List[0].Food_ID;
    var ddl_FoodName = new SelectList(Model.Food_List.OrderBy(f=&gt;f.Food_Name), "Food_ID", "Food_Name", SelectedFood);
 }

 Category:
@Html.DropDownList("ddl_FoodCategories", ddl_FoodCategories)
@Html.DropDownList("ddl_FoodCategoriesName", ddl_FoodCategoriesName)
&lt;br /&gt;
Food:
@Html.DropDownList("ddl_Food", ddl_Food)
@Html.DropDownList("ddl_FoodName", ddl_FoodName)</pre>

**Javascript &#8211; on the .cshtml 頁**

<pre>&lt;script type="text/javascript"&gt;

    $(document).ready(function () {
//在這裡我們做一些 和 SelectedIndexChanged 的 功能 
        //Set up Selected Index Change Like Event For ddl_FoodCategories and #ddl_FoodCategoriesName
        DDL_SelectedIndexChanged('#ddl_FoodCategories', '#ddl_FoodCategoriesName');
        DDL_SelectedIndexChanged('#ddl_FoodCategoriesName', '#ddl_FoodCategories');
        //Set up Selected Index Change Like Event For ddl_Food and #ddl_FoodName
        DDL_SelectedIndexChanged('#ddl_Food', '#ddl_FoodName');
        DDL_SelectedIndexChanged('#ddl_FoodName', '#ddl_Food');
    });

    function DDL_SelectedIndexChanged(DDL1, DDL2) {
//當感到有 .Change event的時候 進行以下的function
        $(DDL1).change(function () {
//把DDL1 的value assign到DDL2上
            $(DDL2).val(this.value);
//如果DDL1是 ddl_FoodCategories或ddl_FoodCategoriesName 時我們要進行一個Jquery 的AJAX Call 
//因為 我們暫時不用為用戶改變ddl_Food或ddl_FoodName 時進行任何特別的動作的.. 所以 便用了 "#ddl_FoodCategories" || DDL1 == "#ddl_FoodCategoriesName"
            if (DDL1 == "#ddl_FoodCategories" || DDL1 == "#ddl_FoodCategoriesName") {
//我們用了RAZOR 的syntax 來建立我們的連結
//用了Jquery的 getJSON方法 向CascadingDropDownList Controller 的 SelectedFoodCategory 取資料
//我們的Parameter是 Food_Category_ID 用來取出和這個Food Category 有關的Food 的資料
                $.getJSON('@Url.Action("SelectedFoodCategory", "CascadingDropDownList")', { Food_Category_ID: this.value }, function (FoodInfo) {
//取得資料後 我們便可以把資料assign 到我們現有的 ddl_Food 和ddl_FoodName上了
                    var ddl_Food = $("#ddl_Food");
                    var ddl_FoodName = $("#ddl_FoodName");
//首先我們要清楚將會被更新的Dropdownlist 的內容 -- 可以使用object.empty() 來實現的
                    ddl_Food.empty();
                    ddl_FoodName.empty();
之後用jquery 的 $.each 來loop though我們的 JSON array
                    $.each(FoodInfo, function (index, FoodInfo) {
//在這裡把Json Array的相關內容加進我們的Dropdownlist上 //這個是給ddl_Food的
                        ddl_Food.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_ID));
/這個是給ddl_FoodName的
                        ddl_FoodName.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_Name))
                    });
                });

            }
        });
    }&lt;/script&gt;</pre>

**完成品**  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f17b257e4ea648c390ad5a13d64cf633/renditions/fullsize.jpg?resize=559%2C278" alt="Cascading Drop Down List completed" width="559" height="278" data-recalc-dims="1" /> 

大家會發現&#8230; 雖然可以做到 **Cascaded DropDownList/級聯下拉框 的效果**.. 但是還有一些美中不足的地方..  
例如.. **Label/DropDownList 大小不一樣**  
和**第二層的下拉框排序有點亂**..

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/79d7c133b98d4d9883186558914b2072/renditions/fullsize.jpg?resize=307%2C351" alt="Cascading Drop Down List Sorting Issue" width="307" height="351" data-recalc-dims="1" />  
Hope you find it useful