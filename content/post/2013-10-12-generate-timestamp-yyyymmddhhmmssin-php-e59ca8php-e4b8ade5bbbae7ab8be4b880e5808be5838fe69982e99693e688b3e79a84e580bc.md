---
id: 2978
title: Generate Timestamp (yyyyMMddhhmmss)in PHP— 在PHP 中建立一個像時間戳的值
date: 2013-10-12T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2978
permalink: '/2013/10/generate-timestamp-yyyymmddhhmmssin-php-%e5%9c%a8php-%e4%b8%ad%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e5%83%8f%e6%99%82%e9%96%93%e6%88%b3%e7%9a%84%e5%80%bc/'
categories:
  - PHP 新手筆記
---
之前和大家介紹過如何在 **TSQL** 和 在 **C# VB .Net上建立一個像時間戳的值**

### <a href="http://blog.sharechiwai.com/2010/11/generate-timestamp-yyyymmddhhmmssin-mssql-2/" rel="bookmark">Generate Timestamp (yyyyMMddhhmmss)in MSSQL — 在MSSQL 中建立一個像時間戳的值</a>

### <a href="http://blog.sharechiwai.com/2010/01/display-timestamp-datetime-as-yyyymmddhhmmss-string-in-net-use-as-filename/" rel="bookmark">Display TimeStamp / DateTime as yyyyMMddHHMMSS string in .Net use as Filename.</a>

今天想和大家分享怎樣在 **PHP** 上建立一個像時間戳的值

解決方法十分簡單 在家可以建立一個**Date Object** 把**format** 設定為 &#8220;**YmdHis**&#8221; 來實現

**解決方法**

**E.G.**

[php]  
$timestamp = date("YmdHis", time());  
[/php]

Hope you find it useful