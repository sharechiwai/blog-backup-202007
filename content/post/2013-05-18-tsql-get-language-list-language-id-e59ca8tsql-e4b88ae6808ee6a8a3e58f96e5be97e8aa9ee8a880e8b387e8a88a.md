---
id: 2881
title: 'TSQL get Language List / Language ID &#8211; 在TSQL 上怎樣取得語言資訊'
date: 2013-05-18T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2881
permalink: '/2013/05/tsql-get-language-list-language-id-%e5%9c%a8tsql-%e4%b8%8a%e6%80%8e%e6%a8%a3%e5%8f%96%e5%be%97%e8%aa%9e%e8%a8%80%e8%b3%87%e8%a8%8a/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
如果想了解在 **SQL Server**上的語言設定資訊..  
或每種語言的格式/顯示表達..  
**E.G.**  
**DateFormat**  
**DateFirst** &#8211; 那一天是一星期的第一天.. E.G. 不同語言都有可能是不同的  
還有用**DateName**時所顯示的文字會是怎樣  
**Microsoft Language ID**  
當然會有**在SQL Server**上的 **Language ID** 以供大家更新 預設語言 時用

<span style="line-height: 1.714285714; font-size: 1rem;">大家可以執行以下的 TSQL 指令</span>

[sql]  
SELECT *  
FROM sys.syslanguages  
[/sql]

**結果:**  
[<img class="alignnone  wp-image-2882" alt="Microsoft SQL Server Language List" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/syslanguage.png?resize=625%2C218" width="625" height="218" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/syslanguage.png)  
Hope you find it useful