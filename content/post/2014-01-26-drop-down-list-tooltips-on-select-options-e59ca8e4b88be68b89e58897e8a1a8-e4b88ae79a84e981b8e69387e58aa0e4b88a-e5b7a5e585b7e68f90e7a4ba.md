---
id: 3018
title: 'Drop Down List Tooltips on Select options &#8211; 在下拉列表 上的選擇加上 工具提示'
date: 2014-01-26T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3018
permalink: '/2014/01/drop-down-list-tooltips-on-select-options-%e5%9c%a8%e4%b8%8b%e6%8b%89%e5%88%97%e8%a1%a8-%e4%b8%8a%e7%9a%84%e9%81%b8%e6%93%87%e5%8a%a0%e4%b8%8a-%e5%b7%a5%e5%85%b7%e6%8f%90%e7%a4%ba/'
categories:
  - HTML/CSS
tags:
  - User Experience
---
還是在提升公司網頁的使用者體驗工作  
今天想和大家分享的是..  
原來在網頁上的 &#8220;**Drop Down List** / **下拉列表**&#8221; 上加上 &#8220;**Tooltips** / **工具提示**&#8221;  
應該是可以**增加使用者體驗**的..  
特別是當你的網頁上有很多已經有很多資料或 已然密密麻麻的時候..  
要在頁面上再加上一段文字去解釋 這個**DropDownList**的選項 有什麼意思&#8230;

解決方法十分簡單..  
我們可以使用 **HTML** 的 **Title** tag 來實現..

**解決方法**

[html]  
<select id="Food Category">  
<option value="fruit" title="Fruit is&#8230;">Fruit</option>  
<option value="meat" title="This is meat option&#8230;">Meat</option>  
<option value="vegetable" title="Vegetable is&#8230;">Vegetable</option>  
</select>  
[/html]

<img class="alignnone" alt="Select Option / DropDownList Tooltips demo" src="https://i1.wp.com/farm8.staticflickr.com/7373/12488544304_08c84ef1ab_d.jpg?resize=500%2C273" width="500" height="273" data-recalc-dims="1" /> 

Demo  
<a title="Select Option ToolTips Demo" href="http://sharechiwai.com/demohtml/selectoption_tooltips" target="_blank">http://sharechiwai.com/demohtml/selectoption_tooltips</a>

Hope you find it useful