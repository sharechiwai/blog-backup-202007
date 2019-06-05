---
id: 1873
title: 'TSQL remove auto-increment properties / column identity from table &#8211; MSSQL 怎樣移除 Auto-increment Properties/ Column上的Identity 屬性'
date: 2011-07-03T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1873
permalink: '/2011/07/tsql-remove-auto-increment-properties-column-identity-from-table-mssql-%e6%80%8e%e6%a8%a3%e7%a7%bb%e9%99%a4-auto-increment-properties-column%e4%b8%8a%e7%9a%84identity-%e5%b1%ac%e6%80%a7/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
今天又是我繼續更新我的程式既日子..  
目標是減小自行手動更改 **Database的Structure**  
要盡量使用**TSQL**/**Stored Procedure**/**SSIS**

今日的難題是..  
怎樣可以**移除 Auto-increment Properties/ Column上的Identity 屬性**  
最後問了朋友之後得到了解決方法  
在**TSQL**上好像是沒有一個**TSQL** 可以直接 **移除 Column上的Identity 屬性** 的

**解決方法:**  
在要移除 Column上的Identity 屬性的 Table/表 上加上新的一個Column

[sql]  
&#8211;ALTER TABLE dbo.[Table\_Name] add [FieldName\_Copy] int  
&#8211;E.G.  
ALTER TABLE dbo.ShareChiWai\_tbl add [ShareChiWai\_ID_Copy] int  
[/sql]

之後我們便要執行 TSQL 來把在Identity Column的內容 複製到新建的Column上

[sql]  
&#8211;UPDATE dbo.[Table\_Name] SET [New\_Field\_Name] = [Old\_Field_Name]  
&#8211;E.G.  
UPDATE dbo.[ShareChiWai\_tbl] SET [ShareChiWai\_ID\_Copy] = [ShareChiWai\_ID]  
[/sql]

完成後我們可以移除 這個Identity Column

[sql]  
ALTER TABLE dbo.[Table\_Name] DROP COLUMN Old\_Field_Name  
E.G.  
ALTER TABLE dbo.[ShareChiWai\_tbl] DROP COLUMN ShareChiWai\_ID  
[/sql]

最後我們便可以用TSQL Command 來更改Column 名了

[sql]  
EXEC sp_rename  
@objname = &#8216;Table_Name.FieldName&#8217;,  
@newname = &#8216;Field\_Name\_Update_To&#8217;,  
@objtype = &#8216;COLUMN&#8217;  
[/sql]

E.G.  
[sql]  
EXEC sp_rename  
@objname = &#8216;ShareChiWai\_tbl.ShareChiWai\_ID_Copy&#8217;,  
@newname = &#8216;ShareChiWai_ID&#8217;,  
@objtype = &#8216;COLUMN&#8217;  
[/sql]

這樣我們便可以**移除 這個Identity Column**  
又可以保留原有的Identity Column的值了

Hope you find it useful