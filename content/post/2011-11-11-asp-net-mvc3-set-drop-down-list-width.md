---
id: 2154
title: ASP.Net MVC3 Set Drop Down List Width
date: 2011-11-11T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2154
permalink: /2011/11/asp-net-mvc3-set-drop-down-list-width/
categories:
  - ASP.Net MVC
---
今天開始Migrate我的 舊Website到 ASP.Net MVC3 上..  
之前的網頁有2對的 Drop Down List 給使用者用來選擇產品的  
[這樣使用者便可以選擇產品編號 或 產品名稱了]

由於default 的 Drop Down List的闊度大小是由Drop Downlist 的內容決定的關係..  
[由第一次Load 進DropDownList 的內容決定.. 所以當我做使用Cascaded DropDownList 時.. 由於他還是以第一次Load進DropDownList 時最濶的內容 為他的闊度Width.. 當你有一些更長的DropDownList 內容時..很可看不能完全看得見 內容的]  
所以在沒有預設闊度的請況下..  
這2對的 Drop Downlist便會不一致了

之前在ASP.Net的 Web Application上我們可以直接修改這個

<div>
  <asp:dropdownlist 控件的屬性, 設定 width=”100”> 等等<br /> 來設定<br /> E.G.<br /> <asp:DropDownList ID=&#8221;ddl_Fruit_ID&#8221; runat=&#8221;server&#8221; AutoPostBack=&#8221;true&#8221;<br /> onselectedindexchanged=&#8221;ddl_Fruit_ID_SelectedIndexChanged&#8221; Width=&#8221;150px&#8221; /><br /> <asp:DropDownList ID=&#8221;ddl_Fruit_Name&#8221; runat=&#8221;server&#8221; AutoPostBack=&#8221;true&#8221;<br /> onselectedindexchanged=&#8221;ddl_Fruit_Name_SelectedIndexChanged&#8221; Width=&#8221;200px&#8221; />
</div>

而用 ASP.Net MVC的話便要使用css style了

解決方法:  
我們可以在建立Drop DownList時放入一個 parameter  
這個Parameter是用來負責 這個控件的css style的

Hope you find it useful