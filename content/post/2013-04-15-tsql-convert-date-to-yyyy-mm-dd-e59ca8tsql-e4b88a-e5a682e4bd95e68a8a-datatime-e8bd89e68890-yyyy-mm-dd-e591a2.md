---
id: 2752
title: 'TSQL Convert Date to YYYY-MM-DD &#8211; 在TSQL 上 如何把 DataTime 轉成 YYYY-MM-DD 呢?'
date: 2013-04-15T00:00:53+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2752
permalink: '/2013/04/tsql-convert-date-to-yyyy-mm-dd-%e5%9c%a8tsql-%e4%b8%8a-%e5%a6%82%e4%bd%95%e6%8a%8a-datatime-%e8%bd%89%e6%88%90-yyyy-mm-dd-%e5%91%a2/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今天在公司**的ASP.Net** 網頁上 需要在**Grid View**上顯示 一些數句日期給用戶看&#8230;  
如果把Table的 **DateTime Field**直接顯示出 **GridView**上&#8230;顯示的格式可能會出現問題

[html]  
<asp:BoundField DataField="dateRequested" HeaderText="Date Requested" />  
[/html]

所以便想使用 **TSQL** 把DateTime轉成 一個指定的格式[**YYYY-MM-DD**]才 output 到**GridView**上

在**TSQL** 上 如何把 **DataTime** 轉成 **YYYY-MM-DD** 呢?

解決方法 十分簡單  
我們只需要使用 **Convert** 把 **format** 設定為 **126** 便可以了

E.G.

**解決方法**:

[sql]  
SELECT CONVERT(VARCHAR(10), GetDate(),126)  
[/sql]

[<img class="alignnone size-full wp-image-2760" alt="TSQL Convert DateTime to YYYY-MM-DD" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/TSQL-YYYY-MM-DD1.jpg?resize=424%2C153" width="424" height="153" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/TSQL-YYYY-MM-DD1.jpg)

Hope you find it useful