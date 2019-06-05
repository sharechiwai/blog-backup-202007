---
id: 965
title: Crystal Report Helper Library on CodePlex
date: 2010-11-16T06:00:56+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=965
permalink: /2010/11/crystal-report-helper-lib/
categories:
  - .Net Tips And Tricks
  - CodePlex
  - Crystal Report Tips and Tricks
  - CrystalReportHelperLib
---
今天發佈了我另一個Library 到**CodePlex** 上&#8230;  
這個**Library** 是我在.Net上使用**Crystal Report XI R2** 的元件時寫的  
方便自己和其他朋友在**.Net Application** 中 使用**Crystal Report的.rpt** 檔 產生/導出報告成**PDF** 的

如果大家也是用**.Net** 和 **Crystal Report**/或者將會考慮使用**Crystal Report** 的話..  
可以嘗試使用這個Library, 看看能不能 令你在.**Net [WinForm]**中更方便地使用**Crystal Report component** 來 產生/導出**PDF**數據資料

以下是小小的Sample Code  
首先我們要到**CodePlex download CrystalReportHelperLib.zip**  
[http://crystalreporthelper.codeplex.com/releases](http://crystalreporthelper.codeplex.com/releases "CrystalReportHelperLib Release")  
把他解壓縮到資料夾上

**CrystalReportHelperLib**  
[http://crystalreporthelper.codeplex.com/](http://crystalreporthelper.codeplex.com/ "CrystalReportHelperLib")

把**CrystalReportHelperLib.dll** 加入到Project 上的參考上  
以下的**Sample Code** 有一個例子, 解釋怎樣使用這個**CrystalReportHelperLib**

[vb]  
Imports CrystalReportHelperLib

Private Sub btn\_GenerateReport\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btn_GenerateReport.Click  
&#8216;建立一個新的Crystal Report Helper  
Dim CReport As New CrystalReportHelper  
Using CReport  
&#8216;初始化報表  
CReport.InitialiseCrystalReport("C:CrystalReportShareChiWaiSample.rpt")  
&#8216;設定數據庫資料  
CReport.SetDataSourceConnection("SQL Server Name", "SQL Database Name", "SQLUsername", "SQLPW")  
&#8216;設定列印時的選項&#8212;這是設定雙面列印的  
CReport.SetPrinterSettingsDuplexDefaultOption()  
&#8216;將會用來Print 這個Report 的 Printer 名稱  
CReport.SetPrinter("Printer PathPrinter Name")  
&#8216;設定報告的 Variable  
CReport.SetParameter("@Period", "Database Variable1")  
CReport.SetParameter("@Period", "Database Variable1")

&#8216;Export PDF  
CReport.ExportCrystalReport("PortableDocFormat", "C:CrystalReportExportShareChiWaiSample.pdf")

&#8216;Print Report  
CReport.PrintAllDoc()  
&#8216;關閉Report  
CReport.Close()  
CReport = Nothing  
End Using  
End Sub  
[/vb]

Hope you find it useful