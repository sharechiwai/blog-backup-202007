---
id: 3698
title: 'EntityFramework with MySQL DateTime Issue  &#8211; Unable to convert MySQL date/time value to System.DateTime'
date: 2016-07-22T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3698
permalink: /2016/07/entityframework-with-mysql-datetime-issue-unable-to-convert-mysql-datetime-value-to-system-datetime/
categories:
  - ASP.Net MVC
tags:
  - Entity Framework 筆記
  - mysql
---
很多時候都會在**Database Table**上建立一個有 **DateTime Field**用來記錄資料修改時間

現在幫另一間公司寫的 **ASP.Net MVC With Entity Framework** 的**Web Application**  
為了減低成本.. 這個Project 選用了**MySQL**  
使用**Entity Framework**　使用**MySQL　**真是一個挑戰。。  
有些的功能沒有直接的　inplementation  
所以久不久便會遇到問題

今次遇到的錯誤信息如下  
&#8220;<span style="color: #ff0000;"><strong>An exception of type &#8216;MySql.Data.Types.MySqlConversionException&#8217; occurred in MySql.Data.dll but was not handled in user Code</strong></span>&#8221;

&#8220;<span style="color: #ff0000;"><strong>Additional information: Unable to convert MySQL date/time value to System.DateTime</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8047/28298853610_2bf423cdac_z.jpg?resize=625%2C591" alt="Unable to convert MySQL date/time value to System.DateTime" width="625" height="591" data-recalc-dims="1" />  
主要是當我嘗試load data時出現..  
**解決方法** 十分簡單  
我𠍒只需要在**Web.config**的 **connection string**上加上以下的設定便可以了

**Convert Zero Datetime=true**

E.g.  
**<add name=&#8221;ProjectTrackerContext&#8221;**  
 **connectionString=&#8221;Database=docker_dev;Data Source=192.168.99.100;User Id=root;Password=password;<span style="color: #0000ff;">Convert Zero Datetime=true</span>&#8220;**  
 **providerName=&#8221;MySql.Data.MySqlClient&#8221; />**

Hope you find it useful