---
id: 27
title: '.Net Export DataGridView / GridView / DataTable To Excel XLSX or PDF &#8212;從DataGridView GridView DataTable 中導出資料到 Excel XLSX 或 PDF'
date: 2010-07-07T07:07:46+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=27
permalink: '/2010/07/net-export-datagridview-gridview-datatable-to-excel-xlsx-or-pdf-%e5%be%9edatagridview-gridview-datatable-%e4%b8%ad%e5%b0%8e%e5%87%ba%e8%b3%87%e6%96%99%e5%88%b0-excel-xlsx-%e6%88%96-pdf/'
jabber_published:
  - "1281853058"
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
早近公司有朋友希望我們可以Export In-house Application [Windows Application] 入面的 table DataGridView 到Excel Spreadsheet中&#8230;  
這樣他們便可以Email 這些資料給客戶了

我終於在這個週末學會了怎樣把 **DataTable/ DataGridView/ GridView Export To Excel SpreadSheet.**  
為了方便大家我把這個功能寫成了個library.  
入面有三個功能  
相對是

<span style="color: #008000;"><strong>ExportDataTableToXLSX</strong></span>  
&#8212; Export DataTable to Excel XLSX or PDF format  
<span style="color: #008000;"><strong>ExportDataGridViewToXLSX</strong></span>  
Export DataGridView to Excel XLSX or PDF format  
<span style="color: #008000;"><strong>ExportGridViewToXLSX</strong></span>  
Export GridView to Excel XLSX or PDF format

由於這個Library 是用 Office 2007/2010 的interop assemblies 來寫的

所以如果你們沒有 Office Primary Interop Assemblies  
可以到以下URL  Download  
Office 2007  
<http://www.microsoft.com/downloads/details.aspx?FamilyID=59daebaa-bed4-4282-a28c-b864d8bfa513&DisplayLang=en>

以下是使用方法

Imports ShareChiWaiLib

<span style="color: #008000;">Public sub Example()<br /> XLSXHelper.ExportDataGridViewToXLSX(&#8220;DataGridView 的名稱&#8221;,<br /> &#8220;True/False 是否包含 Column Header ->這會是DataGridView的 COLUMN HEADER&#8221;,<br /> &#8220;FileType 是 ENUM 例如 ExportFileType.XLSX會Export XLSX Format 的 Excel 2007/2010 檔案<br /> ExportFileType.PDF會成PDF Format的 檔案&#8221;,<br /> &#8220;FilePath 是檔案要Export 到的路徑&#8221;, &#8212; E.G. C:PDF 必需要有這檔案夾的存取權限,<br /> &#8220;FileName &#8211; 檔案名義, 包含 Extension E.g. .xlsx 或 .pdf&#8221;<br /> )<br /> 其餘2個method 和這個差不多..我不加以解釋了</span>

End Sub

大家可以到以下網址download 這個library 🙂

**.Net 4.0**  
<http://sharechiwailib.codeplex.com/releases/>

如果你們發現Bugs或有任何意見/鼓勵等等&#8230;請你們留言給我&#8230;等我加更加多的功力, 令這個Library更好用 =)