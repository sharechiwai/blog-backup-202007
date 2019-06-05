---
id: 2556
title: 'JQuery get number of items inside select list/ dropdownlist &#8211; 使用JQuery來取得在SelectList/ DropDownList上有多小個Item.'
date: 2012-08-18T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2556
permalink: '/2012/08/jquery-get-number-of-items-inside-select-list-dropdownlist-%e4%bd%bf%e7%94%a8jquery%e4%be%86%e5%8f%96%e5%be%97%e5%9c%a8selectlist-dropdownlist%e4%b8%8a%e6%9c%89%e5%a4%9a%e5%b0%8f%e5%80%8bitem/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net
  - dropdownlist
  - Jquery
---
今天公司的**ASP.Net MVC** Website其中有一個Form 有很多**Dynamic**的 資料要取出  
我們要依照不同的選擇顯示不同的內容..  
其中一個情況是

當使用者選擇了一些內容後  
另外的2個**DropDownList**會更新內容&#8230;  
有時候因為資料沒有相符的關係..  
不能Populate 其他的**DropDownList**  
在這個情況下我們便要出示其他的資訊去提示用戶了

所以我們有需要看看怎樣取得DropDownList內有多小個**Item**

原本使用**ASP.Net**的話我們可以使用  
**C#**

[csharp]  
int NumberOfItems = ddl.Items.Count;  
[/csharp]

但是在**ASP.Net MVC**上我們便需要使用**JQuery**來實現了  
假設我們的**DropDownList** 是這樣的  
**HTML**

[html]  
<select id="MinimumContractTerm" name="MinimumContractTerm" class="valid"><option value="1">1 month</option>  
<option value="3">3 months</option>  
<option value="6">6 months</option>  
<option value="12">12 months &#8211; 1 Year</option>  
<option value="24">24 months &#8211; 2 Year</option>  
<option value="36">36 months &#8211; 3 Year</option>  
<option value="48">48 months &#8211; 4 Year</option>  
<option value="60">60 months &#8211; 5 Year</option>  
</select>  
<button id="btn\_run" name="btn\_run">Run</button>  
[/html]

我們可以使用以下的**JQuery** 方法來解決這個問題  
**Javascript**

[javascript]  
$(document).ready(function () {  
$("#btn_run").click(function(){  
alert($("#MinimumContractTerm").length);  
});  
});  
[/javascript]

Hope you find it useful