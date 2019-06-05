---
id: 78
title: .Net Export DataTable To Excel XLSX /PDF
date: 2010-07-08T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/07/08/net-export-datatable-to-excel-xlsx-pdf
permalink: /2010/07/net-export-datatable-to-excel-xlsx-pdf/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8786725071535810754"
categories:
  - .Net Tips And Tricks
---
Last week we had a meeting other friends at work, they has some ideas about the enhancement of the in-house application. E.g. export the data from the in-house application to Spreadsheet, which would be very handy when you need to keep a record of the query you done or need to email the data to the client&#8230;etc. I have spent sometime in the weekend and see how to achieve that. finally, I have created a simple library to Export DataTable/ DataGridView / Grid View to Excel XLSX or PDF format.

Here is my **.Net Library**: &#8220;**ShareChiWaiLib**&#8221; at the moment it only has 1 class &#8220;**XLSXHelper**&#8220;, which allow user to  
**Export DataTable to Excel XLSX or PDF**  
By using XLSXHelper. ExportDataTableToXLSX() method

**Export DataGridView to Excel XLSX or PDF**  
By using XLSXHelper. ExportDataGridViewToXLSX() method

**Export GridView to Excel XLSX or PDF**  
By using XLSXHelper. ExportGridViewToXLSX() method

Here it is the description about this class.

<span style="color: #38761d;">Imports ShareChiWaiLib</span><br style="color: #38761d;" /><br style="color: #38761d;" /><span style="color: #38761d;">Public sub Example()</span><br style="color: #38761d;" /> <span style="color: #38761d;">XLSXHelper.ExportDataGridViewToXLSX(&#8220;DataGridView Name&#8221;,</span><br style="color: #38761d;" /> <span style="color: #38761d;">&#8220;True/False &#8212; whether to includes the column header&#8221;,</span><br style="color: #38761d;" /> <span style="color: #38761d;">&#8220;FileType &#8212; is ENUM E.g. ExportFileType.XLSX to Export XLSX Format in Excel 2007/2010</span><br style="color: #38761d;" /> <span style="color: #38761d;">ExportFileType.PDF is for PDF Format&#8221;,</span><br style="color: #38761d;" /> <span style="color: #38761d;">&#8220;FilePath &#8212; where you want the file export to and please ensure you have premission to write to that directory,</span><br style="color: #38761d;" /> <span style="color: #38761d;">&#8220;FileName &#8211; Filename includes file Extension E.g. &#8216;.xlsx&#8217; or &#8216;.pdf'&#8221;</span><br style="color: #38761d;" /> <span style="color: #38761d;">)</span><br style="color: #38761d;" /><br style="color: #38761d;" /><span style="color: #38761d;">&#8216;XLSXHelper.ExportGridViewToXLSX</span><br style="color: #38761d;" /><span style="color: #38761d;">&#8216;XLSXHelper.ExportDataGridViewToXLSX</span><br style="color: #38761d;" /><span style="color: #38761d;">&#8216;are similar, therefore I will leave it to you to find out =)</span><br style="color: #38761d;" /> <span style="color: #38761d;"></span>  
<span style="color: #38761d;">End Sub</span>

Feel Free to download the Library from the URL below.  
.Net 2.0  
<http://www.hongkongcu.net/isaac/.Net2.0/ShareChiWaiLib/ShareChiWaiLib.zip>  
.Net 3.5  
<http://www.hongkongcu.net/isaac/.Net3.5/ShareChiWaiLib/ShareChiWaiLib.dll>  
.Net 4.0  
<http://sharechiwailib.codeplex.com/releases/>

If you do not have office in you computer, you may need to download **Office Primary Interop Assemblies**, in order to get it work  
 ****  
**Office 2007**  
<http://www.microsoft.com/downloads/details.aspx?FamilyID=59daebaa-bed4-4282-a28c-b864d8bfa513&DisplayLang=en>

I will try to put more feature, useful stuff on &#8220;**ShareChiWaiLib**&#8221; in future. I would be grateful, if you could give me some suggestion/feedback about **ShareChiWaiLib** and  what to put in future=).

Hope you find it useful