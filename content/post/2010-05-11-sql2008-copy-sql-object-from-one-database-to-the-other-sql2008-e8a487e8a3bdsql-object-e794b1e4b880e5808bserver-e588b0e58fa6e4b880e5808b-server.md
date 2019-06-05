---
id: 142
title: 'SQL2008 Copy SQL Object from one database to the other&#8212; SQL2008 複製SQL Object 由一個SERVER 到另一個 SERVER'
date: 2010-05-11T00:00:00+08:00
author: ShareChiWai
layout: post
guid: 'http://sharechiwai.wordpress.com/2010/05/11/sql2008-copy-sql-object-from-one-database-to-the-other-sql2008-%e8%a4%87%e8%a3%bdsql-object-%e7%94%b1%e4%b8%80%e5%80%8bserver-%e5%88%b0%e5%8f%a6%e4%b8%80%e5%80%8b-server'
permalink: '/2010/05/sql2008-copy-sql-object-from-one-database-to-the-other-sql2008-%e8%a4%87%e8%a3%bdsql-object-%e7%94%b1%e4%b8%80%e5%80%8bserver-%e5%88%b0%e5%8f%a6%e4%b8%80%e5%80%8b-server/'
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "5884292006303958483"
categories:
  - MSSQL Tips and Tricks
---
兩個星期前 公司把一個SQL SERVER 由**SQL2000** 升級到**SQL2008**  
雖然升級過程不算太順利&#8230;  
因為如果要在SQL2008 執行DTS PACKAGE 要在電腦上做多一些東西  
和有一些CODE 不能順利UPGRADE 到SQL2008

昨天難題終於出現了&#8230;  
就是有位朋友寫的一個複製**SQL OBJECT** 的功能不能在**SQL2008** 上運行&#8230;  
所以現在便要想想怎樣可以把SQL OBJECT 從一個DATABASE完完整整地複製到另一個DATABASE.

曾經想過用以下的方法  
1)  
<span style="color: #38761d;">SELECT * INTO DatabaseName.dbo.DestinationTableName</span><br style="color: #38761d;" /><span style="color: #38761d;">FROM DatabaseName.dbo.SourceTableName</span>  
只會把資料複製&#8230;  
而**不能把預設值和其他CONSTRAINT** 複製到新的資料表上

2) 如果我們先建立好所需要的資料表 E.G. 設定所有的預設值和其他CONSTRAINT

之後再加入資料..,這便不能保留AUTONUMBER 的原本數值  
如果你有很多的TABLE 的話&#8230;你便需要用很長時間來做這個動作了

3) 最後我便想到用&#8221;**SQL Server Integration Services**&#8221; (**SSIS**) 來做這個動作了  
以下是我用**SSIS** 的步驟:  
1) 首先要做的是啟動 &#8220;**SQL Server Business Intelligent Studio**&#8221;  
建立一個&#8221;**Integration Service Project**&#8221;  
2) 在**TOOLBOX** 中 選擇 &#8220;**Transfer SQL Server Object Task**&#8221; 之後Drag & Drop 到**Control Flow** 入1面1  
3) Right Click ->&#8221;**Edit**&#8221; 去edit 這個 &#8220;**Transfer SQL Server Object Task**&#8221;  
4) 在&#8221;**General Tab**&#8221; 中可以&#8221;Name&#8221; 的text box 給他個有意思的名字  
5) Click去 &#8220;**Objects Tab**&#8221;  
6) &#8220;**Transfer SQL Server Object Task**&#8221; 和 &#8220;**Data Transfer Task**&#8221; 的設定有一些不同,

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="http://sharechiwai.files.wordpress.com/2010/05/connection.jpg"><img src="http://sharechiwai.files.wordpress.com/2010/05/connection.jpg?w=300&#038;resize=400%2C250" border="0" alt="" width="400" height="250" data-recalc-dims="1" /></a>
</div>

就是 &#8220;**Data Transfer Task**&#8221; 可以在**Connection Manager** 中選取 你要用的**CONNECTION** [如果你之後已經設定了一個的話]  
而&#8221;**Transfer SQL Server Object Task**&#8221; 的connection 不可以在**Connection Manager** 中選取的  
所以便要做 **Connection** 中的 **Source Connection**/ **Source Database**/ **Destination Connection** 和 **Destination Database**中設定

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i2.wp.com/farm6.static.flickr.com/5109/5687810497_fa1572ef45.jpg"><img style="border: 0px initial initial;" src="https://i2.wp.com/farm6.static.flickr.com/5109/5687810497_fa1572ef45.jpg?w=625" border="0" alt="" data-recalc-dims="1" /></a>
</div>

7) 設定好 Connection之後便可以選擇 要複製那些SQL Object了  
這裡分開了5個部分

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i0.wp.com/farm6.static.flickr.com/5302/5687812321_27509d0fdb.jpg"><img style="border: 0px initial initial;" src="https://i0.wp.com/farm6.static.flickr.com/5302/5687812321_27509d0fdb.jpg?w=625" border="0" alt="" data-recalc-dims="1" /></a>
</div>

**Connection**  
用來設定那個是**Source Database** 和 **Destination Database**  
**Destination**  
用來設定複製到新的資料表上的動作  
E.G. 如果資料表已出現在 **Destination Database** 要不要 DROP 他  
需要複製**Data**/**Schema**/**Collation**/**ExtendedProperties** 和其他和他有關的資料表嗎&#8230;ETC

**Destination Copy Options**  
這是最重要的一部分  
給你選擇那些Table/View/Stored Procedure/ Use Define function/Schema 等等的SQL Object

**Security**  
這是給你選擇那些和Security有關的Object 你想複製到新的資料表上  
**  
Table Options**  
給你選擇是否把 **Index**/ **Trigger**/ **Primary Key**/ **Foreign Key** &#8230;etc 都複製到新的資料表上

用法都算是十分簡單..所以我都不加以解釋了

如果有問題的話可以或我的concept不太正確的話請留言給我 改正我的錯誤

Hope you find it useful =)