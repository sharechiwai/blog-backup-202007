---
id: 2152
title: 'Crystal Report Viewer in WPF &#8211; 如何在WPF 上使用Crystal Report Viewer'
date: 2012-01-16T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2152
permalink: '/2012/01/crystal-report-viewer-in-wpf-%e5%a6%82%e4%bd%95%e5%9c%a8wpf-%e4%b8%8a%e4%bd%bf%e7%94%a8crystal-report-viewer/'
categories:
  - WPF
tags:
  - Crystal Report
---
今天..公司的同事突然叫我寫一個管理我們研究/開發的程式&#8230;  
[主要都是用來記下 所做過的Task]  
由於他說是Urgent的關係..所以我便用了WinForm來開發..  
到有多點空閒時間時才用WPF 寫&#8230;  
[主要是因為自己對WPF 不太熟練的關係]  
第一個難題是..怎樣可以把**Crystal Report Viewer** 放進**WPF User Control** 內..  
我使用的是 **Crystal Report X1 R2**&#8230;比較舊..所以不太清楚能不能支援..

做了一些research之後..終於找到解決方法了

**解決方法**:  
首先我們要為我們的**WPF project**加上一些和**WinForm**有關的 assemible  
他們是

之後當然要加入Crystal Report的 assemible

你需要加入以下參考  
Crystal Report for .Net Framework  
CrystalDecisions.CrystakReports.Engine  
CrystalDecisions.ReportSource  
CrystalDecisions.Shared  
CrystalDecisions.VSDesigner  
CrystalDecisions.Windows.Forms

之後在User Control 的加入Namespace的位置的地方加入 Crystal Report的參考

最後在User Control上加入以下的程式碼便可以了  
我建立了一個簡單的Crystal Report 用來示範這個User Control真的可以顯示Crystal Report的內容的  
之後在Loaded Event上加入 以下的程式碼去 Load 這個Report到Crystal Report Viewer上

C Sharp

[csharp]  
CrystalReportViewer rptViewer = new CrystalReportViewer();  
WindowsFormsHost host = new WindowsFormsHost();  
rptViewer.ReportSource = report;  
host.Child = rptViewer;  
reportGrid.Children.Add(host); //Add report viewer in WPF Grid  
[/csharp]

Hope you find it useful