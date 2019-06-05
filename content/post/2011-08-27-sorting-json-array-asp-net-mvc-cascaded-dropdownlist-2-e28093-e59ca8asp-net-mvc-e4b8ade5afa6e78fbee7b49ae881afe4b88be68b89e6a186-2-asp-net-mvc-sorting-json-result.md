---
id: 2025
title: 'Sorting JSON Array &#8211; ASP.Net MVC Cascaded DropDownList 2 – 在ASP.Net MVC 中實現級聯下拉框 2 &#8211; ASP.net MVC Sorting JSON result'
date: 2011-08-27T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2025
permalink: '/2011/08/sorting-json-array-asp-net-mvc-cascaded-dropdownlist-2-%e2%80%93-%e5%9c%a8asp-net-mvc-%e4%b8%ad%e5%af%a6%e7%8f%be%e7%b4%9a%e8%81%af%e4%b8%8b%e6%8b%89%e6%a1%86-2-asp-net-mvc-sorting-json-result/'
categories:
  - ASP.Net MVC
tags:
  - ASP.net MVC Sorting JSON result
  - Cascading Drop Down List
  - Jquery
  - Json Array
  - JSON Array 排序
  - Sorting Json Array
---
在上一個Post 介紹了怎樣在**ASP.Net MVC** 上使用**Cascaded DropDownList  
** 

# <a title="Permalink to ASP.Net MVC Cascaded DropDownList – 在ASP.Net MVC 中實現級聯下拉框" href="http://blog.sharechiwai.com/2011/08/asp-net-mvc-cascaded-dropdownlist-%e5%9c%a8asp-net-mvc-%e4%b8%ad%e5%af%a6%e7%8f%be%e7%b4%9a%e8%81%af%e4%b8%8b%e6%8b%89%e6%a1%86/" rel="bookmark">ASP.Net MVC Cascaded DropDownList – 在ASP.Net MVC 中實現級聯下拉框</a>

和另一個**Post** 介紹怎麼在 **Razor cshtml/vbhtml** 上幫 **Drop Down List 進行排序  
** 

# <a title="Permalink to ASP.Net Web Application To ASP.Net MVC Notes II Drop Down List Sorting DropDownList- ASP.Net Web Application To ASP.Net MVC 新手筆記II Drop Down List 排序" href="http://blog.sharechiwai.com/2011/08/asp-net-web-application-to-asp-net-mvc-notes-ii-drop-down-list-sorting-dropdownlist-asp-net-web-application-to-asp-net-mvc-%e6%96%b0%e6%89%8b%e7%ad%86%e8%a8%98ii-drop-down-list-%e6%8e%92%e5%ba%8f/" rel="bookmark">ASP.Net Web Application To ASP.Net MVC Notes II Drop Down List Sorting DropDownList- ASP.Net Web Application To ASP.Net MVC 新手筆記II Drop Down List 排序</a><span class="Apple-style-span" style="color: #333333; font-weight: 300;"><strong> </strong></span>

但是還是有一個美中不足的地方&#8230;  
就是 如果我們的資料不是順序排列的話&#8230;  
那個**DropDownList** 便會有點難看了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/79d7c133b98d4d9883186558914b2072/renditions/fullsize.jpg?resize=307%2C351" alt="Unsorted Cascading Drop Down List" width="307" height="351" data-recalc-dims="1" />  
由於之前的 **ASP.NET MVC** 上 的**Cascaded DropDownList是用 Ajax Call 來取得JSON Array** 之後再進行**DataBind**鎖定到 **DropDownList** 上..  
所以我們便不可以 用**ASP.Net** 的功能來把資料進行**Sorting**/排序了

經過了一段時間在網上進行Research 後.. 終於找到了一個 自定的 **Javascript function** 來把 **JSON Array 排序**&#8230;  
以下是這個 **Function** 的Code

在頁面上加入了 這個Function 後  
我們便可以用 這個**function** 來解決**sorting** 的問題了

<pre>&lt;script type="text/javascript"&gt;
 //一個Javascript的功能用來做ordering 的
    //Field是屬性的名稱
    //Desc 是定義是否用倒序方法 true,false
    function OrderBy(Field, Desc, Primer) {
    //如果Desc = true 的話 用 -1 otherwise用 1
        if (Desc) {
            Desc = -1
        }
        else {
            Desc = 1
        }
        //下面做comparison
        return function (a, b) {
            a = a[Field];
            b = b[Field];
            if (typeof (Primer) != 'undefined') {
                a = Primer(a);
                b = Primer(b);
            }

            if (a &lt; b) return Desc * -1;
            if (a &gt; b) return Desc * 1;
            return 0;
        }
    }
&lt;/script&gt;</pre>

** 將會被更給的Javascript**

<pre>$.each(FoodInfo, function (index, FoodInfo) {
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
                    });</pre>

** 已更變的Javascript**

<pre>//要更變的地方
                    //因為現在2個DropDownList databind的內容的次序不同了
                    //所以要分開來re-populate2個dropdownlist
                    //正常的
                    $.each(FoodInfo, function (index, FoodInfo) {
                        ddl_Food.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_ID));
                    });
                    //把第一個Json Array的Value Assign到一個暫用的Variable上.. 以令被選中的DropDownList Value一致
                    TempFood = FoodInfo[0].Food_ID;
                    //現在我們要使用Sorting來把
                    FoodInfo = FoodInfo.sort(OrderBy('Food_Name', false, function (a) { return a.toUpperCase() }));
                    $.each(FoodInfo, function (index, FoodInfo) {
                        ddl_FoodName.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_Name));
                    });
                    //如果TempFood 不是空白時 我們把他的Selected Value完成ddl_Food 現在SelectedValue
                    if (TempFood != "") {
                        $("ddl_FoodName").val(TempFood);
                    }</pre>

**Cascading DropDownList 所用的 Javascript在這裡**

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
//要更變的地方
                    //因為現在2個DropDownList databind的內容的次序不同了
                    //所以要分開來re-populate2個dropdownlist
                    //正常的
                    $.each(FoodInfo, function (index, FoodInfo) {
                        ddl_Food.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_ID));
                    });
                    //把第一個Json Array的Value Assign到一個暫用的Variable上.. 以令被選中的DropDownList Value一致
                    TempFood = FoodInfo[0].Food_ID;
                    //現在我們要使用Sorting來把
                    FoodInfo = FoodInfo.sort(OrderBy('Food_Name', false, function (a) { return a.toUpperCase() }));
                    $.each(FoodInfo, function (index, FoodInfo) {
                        ddl_FoodName.append(
                        $('&lt;option/&gt;')
                            .attr('value', FoodInfo.Food_ID)
                            .text(FoodInfo.Food_Name));
                    });
                    //如果TempFood 不是空白時 我們把他的Selected Value完成ddl_Food 現在SelectedValue
                    if (TempFood != "") {
                        $("ddl_FoodName").val(TempFood);
                    }
                });

            }
        });</pre>

<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f709e57c3bd14aaab7c48fd92dea76ab/renditions/fullsize.jpg?resize=319%2C438" alt="Cascading Drop Down List Sorted" width="319" height="438" data-recalc-dims="1" /> 

Hope you find it useful