---
id: 3332
title: '.Net Convert DataTable to Json &#8211; 如何把DataTable轉換成Json Object'
date: 2014-12-01T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3332
permalink: '/2014/12/net-convert-datatable-to-json-%e5%a6%82%e4%bd%95%e6%8a%8adatatable%e8%bd%89%e6%8f%9b%e6%88%90json-object/'
categories:
  - .Net Tips And Tricks
tags:
  - AngularJs
  - Json.Net
---
今天終於可以繼續在公司做**ASP.Net MVC**的Project了..  
由於最近學了**AngularJs** 所以便喜歡把資料轉成 **json**  
之後放在**Angular**上使用..

**解決方法**十分簡單

我們可以使用**Json.Net**  
大家可以使用 **Nuget**來安裝 **Json.Net**

<div style="width: 650px" class="wp-caption alignnone">
  <img class="" src="https://i0.wp.com/farm9.static.flickr.com/8674/15931446681_68e3f32d16_z.jpg?resize=625%2C146" alt="" width="625" height="146" data-recalc-dims="1" />
  
  <p class="wp-caption-text">
    Install Json.NET via NuGet
  </p>
</div>

之後做可以使用<span style="color: #008000;"><strong>JsonConvert.SerializeObject()</strong></span>這個功能來把 **DataTable**轉成**Json** Object  
E.g.

<pre>// Convert DataTable to Json as a String
string json = JsonConvert.SerializeObject(tbl, new DataTableConverter());
//output result
console.log(json);
</pre>

Hope you find it useful