---
id: 3202
title: '.Net Convert DataRow to List of String with DataType Filter- .Net 把DataRow使用數據類型篩選的結果 轉成 字符串列表'
date: 2014-05-30T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3202
permalink: '/2014/05/net-convert-datarow-to-list-of-string-with-datatype-filter-net-%e6%8a%8adatarow%e4%bd%bf%e7%94%a8%e6%95%b8%e6%93%9a%e9%a1%9e%e5%9e%8b%e7%af%a9%e9%81%b8%e7%9a%84%e7%b5%90%e6%9e%9c-%e8%bd%89%e6%88%90/'
categories:
  - .Net Tips And Tricks
tags:
  - DataTable
---
在之前的網誌和大家分享了如何 把**DataRow** 的內容 轉成**List Of String  
** 

<h3 class="entry-title" style="font-weight: normal;">
  <a style="color: #0f3647;" href="http://blog.sharechiwai.com/2014/05/net-convert-datarow-to-list-of-string-net-%e6%8a%8adatarow-%e8%bd%89%e6%88%90-%e5%ad%97%e7%ac%a6%e4%b8%b2%e5%88%97%e8%a1%a8/" rel="bookmark">.Net Convert DataRow to List of String – .Net 把DataRow 轉成 字符串列表</a>
</h3>

今天發現原來他有一個很好的功能可以方便大家去**Filter**/ **篩選 DataRow**上某一種的**DataType**才 Return出來

我們可以使用<span style="color: #008000;"><strong>.OfType<[Data Type]>()</strong> </span>這個功能&#8230;在**ItemArray**的結果上加以篩選

E.g. 如果我想把這個**DataRow**上的String Field 取出來.. 我們可以使用

<pre>// 把DataRow的ItemArray 把DataRow Field 轉成了Array...之後使用ofType() 這個功能
	// 去 篩選 想取出的數據類型 E.G. String Data Type 
	// 如果想把他們轉成List我們可以像在之前的網誌一樣用LINQ 把內容轉成 List Of String 
	List contents = dr1.ItemArray.OfType().Select(c =&gt; Convert.ToString(c)).ToList(); 
	
</pre>

**Full Source Code**

<pre>DataTable tbl = new DataTable();
    tbl.Columns.Add(new DataColumn("Food_ID", Type.GetType("System.String")));
    tbl.Columns.Add(new DataColumn("Food_Name", Type.GetType("System.String")));
    tbl.Columns.Add(new DataColumn("Price", Type.GetType("System.Decimal")));
    tbl.Columns.Add(new DataColumn("FoodCategory_ID", Type.GetType("System.String")));
            
    // Create Data Row
    DataRow dr1 = tbl.NewRow();
    dr1["Food_ID"] = "00001";
    dr1["Food_Name"] = "Apple";
    dr1["Price"] = 0.99;
    dr1["FoodCategory_ID"] = "00001";
    tbl.Rows.Add(dr1);
	
	// 把DataRow的String Data Type 的Field Extract 出來成List Of String 
	List contents = dr1.ItemArray.OfType().Select(c =&gt; Convert.ToString(c)).ToList(); 
	
	// 輸出結果 - List Of String上有多小 Item
	Console.WriteLine("Number of Items in List of String: " + contents.Count().ToString() );
	
	//使用For Loop把 結果輸出 - 0.99 不在List內..因為他的DataType是 Decimal
	for(int i = 0; i&lt;contents.Count; i++ ){
		Console.WriteLine(contents[i]);
	}
</pre>

<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5560/14423680643_9d52317422_z.jpg?resize=625%2C508" alt=".Net Convert Data Row to List of String with Filter" width="625" height="508" data-recalc-dims="1" /> 

Hope you find it useful