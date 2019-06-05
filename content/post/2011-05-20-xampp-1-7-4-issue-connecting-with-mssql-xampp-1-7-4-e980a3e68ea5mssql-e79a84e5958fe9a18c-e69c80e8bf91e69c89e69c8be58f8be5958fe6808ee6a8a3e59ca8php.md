---
id: 1851
title: 'XAMPP 1.7.4 Issue &#8211; connecting with MSSQL &#8211; XAMPP 1.7.4 連接MSSQL 的問題 最近有朋友問怎樣在PHP 上連接Microsoft SQL Server'
date: 2011-05-20T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1851
permalink: '/2011/05/xampp-1-7-4-issue-connecting-with-mssql-xampp-1-7-4-%e9%80%a3%e6%8e%a5mssql-%e7%9a%84%e5%95%8f%e9%a1%8c-%e6%9c%80%e8%bf%91%e6%9c%89%e6%9c%8b%e5%8f%8b%e5%95%8f%e6%80%8e%e6%a8%a3%e5%9c%a8php/'
categories:
  - PHP 新手筆記
tags:
  - MSSQL
  - XAMPP
---
由於我是使用 **XAMPP1.7.3**的所以只是replace了**<span style="color: #3366ff;">ntwdblib.dll</span>**  
和**uncomment** 了** <span style="color: #339966;">extension=php_mssql.dll</span>** 使解決了 連接MSSQL 的問題

可惜我的解決方法解決不了我朋友的問題..  
最後發現他使用的版本和我的有所不同..  
[他是使用 **XAMPP 1.7.4**的]

為了方便測試問題  
所以我便升級了我的**XAMPP**了  
之後發現 原來**XAMPP 1.7.4缺小了很多DLL**

幸好..我的電腦上還有1.7.3版本..  
所以當我把缺小了的DLL 複製到 適合的資料夾便可以了  
**<span style="color: #3366ff;">php_mssql.dll</span>**  
** <span style="color: #3366ff;">ntwdblib.dll</span>**

大家也可以到以下URL Download  
 [https://skydrive.live.com/?cid=66398506b8d4b8bf&sc=documents&uc=2&id=66398506B8D4B8BF%21125#](https://skydrive.live.com/?cid=66398506b8d4b8bf&sc=documents&uc=2&id=66398506B8D4B8BF%21125#)

詳情可以參考以下**URL**  
 <a title="PHP Connect to MSSQL Issue 1 – Fatal error: Call to undefined function mssql_connect() – PHP 連接MSSQL Database" href="http://blog.sharechiwai.com/2011/05/php-connect-to-mssql-issue-1-fatal-error-call-to-undefined-function-mssql_connect-php-%E9%80%A3%E6%8E%A5mssql-database/" target="_blank">PHP Connect to MSSQL Issue 1 – Fatal error: Call to undefined function mssql_connect() – PHP 連接MSSQL Database</a>

<a title="PHP Connect to MSSQL Issue 1 Part2 – PHP Startup: Unable to load dynamic Library ‘\xampp\php\ext\php_mssql.dll’ – The specified module could not be found PHP 連接MSSQL Database 問題" href="http://blog.sharechiwai.com/2011/05/php-connect-to-mssql-issue-1-part2-php-startup-unable-to-load-dynamic-library-xamppphpextphp_mssql-dll-the-specified-module-could-not-be-found-php-%e9%80%a3%e6%8e%a5mssql-database/" target="_blank">PHP Connect to MSSQL Issue 1 Part2 – PHP Startup: Unable to load dynamic Library ‘\xampp\php\ext\php_mssql.dll’ – The specified module could not be found PHP 連接MSSQL Database 問題</a>

<a title="PHP Connect to MSSQL Issue 2 – Warning mssql_connect()[function.mssql-connect]: Unable to connect to server: – PHP 連接MSSQL Database 問題 2" href="http://blog.sharechiwai.com/2011/05/php-connect-to-mssql-issue-2-warning-mssql_connectfunction-mssql-connect-unable-to-connect-to-server-php-%E9%80%A3%E6%8E%A5mssql-database-%E5%95%8F%E9%A1%8C-2/" target="_blank">PHP Connect to MSSQL Issue 2 – Warning mssql_connect()[function.mssql-connect]: Unable to connect to server: – PHP 連接MSSQL Database 問題 2</a>

Hope you find it useful