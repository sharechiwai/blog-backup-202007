---
id: 3199
title: '.Net Convert DataRow to List of String &#8211; .Net 把DataRow 轉成 字符串列表'
date: 2014-05-28T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3199
permalink: '/2014/05/net-convert-datarow-to-list-of-string-net-%e6%8a%8adatarow-%e8%bd%89%e6%88%90-%e5%ad%97%e7%ac%a6%e4%b8%b2%e5%88%97%e8%a1%a8/'
categories:
  - .Net Tips And Tricks
tags:
  - DataTable
---
今天需要幫公司寫一個**Export CSV** 的**Module**  
由于**Database**上的資料有機會令到 Export 到CSV上的數據無法再讀回到一個**DataTable**上  
E.G. 如果數據上有一些 S**peech Mark** 或 **comma**的話..

有機會令到讀的程式當他們是另一個**CSV Field**  
所以便要寫一個功能去把**DataRow**的**Field Extract** 出來之後再在每一個Filter上Escape那些有機會構成問題的Field  
之後再Export 成CSV  
大家可以使用For Loop來把Field Extract出來..  
我比較喜歡用**LINQ** 因為他可以減少程式碼的數量

如何可以把**DataRow** 轉成**List Of String** 呢?

**解決方法** 十分簡單  
我們可以使用DataRow的 **ItemArray**功能把 **DataRow**的**內容 Export成Array**..  
之後便用**LINQ** 的方法把**ItemArray**的內容轉換成 **String**  
之後再用**.ToList()**這個方法把這個 **LINQ**的結果轉成**List**便可以了

我會使用之前和大家分享的Sample DataTable  和大家作一個示範

<a title="Sample data for DataTable for testing – 我的DataTable 的 資料樣本" href="http://blog.sharechiwai.com/2011/07/sample-data-for-datatable-for-testing-%e6%88%91%e7%9a%84datatable-%e7%9a%84-%e8%b3%87%e6%96%99%e6%a8%a3%e6%9c%ac/" target="_blank">Sample data for DataTable for testing – 我的DataTable 的 資料樣本</a>  
E.G. 使用**LINQ** 把 **DataRow** 的 **ItemArray** 輸出的結果轉換成**List Of String**

<pre>// 把DataRow的Field Extract出來成List Of String 
	List contents = dr1.ItemArray.Select(c =&gt; Convert.ToString(c)).ToList(); 
</pre>

**Full Sample Code:**

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
	
	// 把DataRow的Field Extract出來成List Of String 
	List contents = dr1.ItemArray.Select(c =&gt; Convert.ToString(c)).ToList(); 
	
	// 輸出結果 - List Of String上有多小 Item
	Console.WriteLine("Number of Items in List of String: " + contents.Count().ToString() );
	
	//使用For Loop把 結果輸出
	for(int i = 0; i&lt;contents.Count; i++ ){
		Console.WriteLine(contents[i]);
	}
</pre>

**結果:**  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2908/14217066237_c254948fec_z.jpg?resize=625%2C525" alt=".Net - Convert DataRow to List of String" width="625" height="525" data-recalc-dims="1" />  
Hope you find it useful