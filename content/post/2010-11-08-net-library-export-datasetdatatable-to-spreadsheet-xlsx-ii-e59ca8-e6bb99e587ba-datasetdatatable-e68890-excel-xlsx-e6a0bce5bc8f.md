---
id: 877
title: '.Net Library Export DataSet/DataTable to SpreadSheet (XLSX) II &#8212; 在 滙出 DataSet/DataTable 成 Excel XLSX 格式'
date: 2010-11-08T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=877
permalink: '/2010/11/net-library-export-datasetdatatable-to-spreadsheet-xlsx-ii-%e5%9c%a8-%e6%bb%99%e5%87%ba-datasetdatatable-%e6%88%90-excel-xlsx-%e6%a0%bc%e5%bc%8f/'
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
  - CodePlex
---
最近&#8230;公司的新網頁需要一個功能..要輸出網頁上的一些資料成 **Excel Spreadsheet**..上星期測試了自己之前寫的 **ShareChiWaiLib** 的 **XLSXHelper**&#8230; 能夠成功在本機測試..可以打資料由**DataSet/DataTable/GridView 上輸出到 XLSX**&#8230; 很可惜真正的發報到 Server 時出現以下的  錯誤信息&#8230;  
**<span style="color: #ff0000;">&#8220;Retrieving the COM class factory for component with CLSID {00024500-0000-0000-C000-000000000046} failed due to the following error: 80070005 Access is denied. (Exception from HRESULT: 0x80070005 (E_ACCESSDENIED)). &#8220;</span>**

和朋友一起想了很久也想不通怎麼解決&#8230;  
其中一個原因是不想在Server 上再安裝其他軟件..E.G. **Office**&#8230;最後終於放棄了 用**XLSXHelper** &#8230;

經過一段時間的努力..終於學會怎樣使用 **Open XML SDK** 來做到把**DataSet/DataTable Export 到 Spreadsheet [XLSX format 了]**

我把Source Code 發佈了**CodePlex** 上.. 大家有興趣的請一起研究研究..令這個Library 更好用&#8230;方便其他遇到同樣問題的朋友  
<http://sharechiwailib.codeplex.com/>

大家可以到以下URL Download 最近Compile 有**OpenXMLXLSXHelper** 的 DLL

<http://sharechiwailib.codeplex.com/releases/view/55256>

[vb]  
Imports ShareChiWaiLib  
Dim tbl as DataTable = Get_DataTableForTesting() &#8216; 這是你取DataTable的一個功能

Dim ds as DataSet = Get_DataSetForTesting() &#8216; 這是你取DataSet的一個功能

Dim XLSXExporter As New OpenXMLXLSXHelper

XLSXExporter.ExportDatatableToXLSX(tbl, "D:DestinationFolder", "DataTable.xlsx", True, "ExampleSheet", 1)

XLSXExporter.ExportDataSetToXLSX(ds, "D:DestinationFolder", "DataSet.xlsx", True, 1)

解釋  
XLSXExporter.ExportDatatableToXLSX(DataTable, 儲存位置, 儲存的, 是否使用Table Column Header 為Column 名, "Sheet Name", 第一行的Index 由1開始)

XLSXExporter.ExportDataSetToXLSX(DataSet, 儲存位置, 儲存的, 是否使用Table Header 為Column 名, 第一行的Index 由1開始)

[/vb]

Hope you find it useful  
有時間的時候我會做一些範例來..令到這個Library 更加容易明白&#8230;更加容易使用  
Have a good day =)