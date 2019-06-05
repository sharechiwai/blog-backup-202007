---
id: 1838
title: 'PHP Connect to MSSQL Issue 1 Part2 &#8211; PHP Startup: Unable to load dynamic Library &#8216;\xampp\php\ext\php_mssql.dll&#8217; &#8211; The specified module could not be found PHP 連接MSSQL Database 問題'
date: 2011-05-23T00:00:31+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1838
permalink: '/2011/05/php-connect-to-mssql-issue-1-part2-php-startup-unable-to-load-dynamic-library-xamppphpextphp_mssql-dll-the-specified-module-could-not-be-found-php-%e9%80%a3%e6%8e%a5mssql-database/'
categories:
  - PHP 新手筆記
tags:
  - MSSQL
  - PHP
  - XAMPP
---
昨天寫了當大家遇到  
&#8220;**<span style="color: #ff0000;">Fatal error: Call to undefined function mssql_connect()</span>**&#8221;  
應該怎樣做..  
有些朋友可能是因為**XAMPP** 版本不同的關係.所以仍然還是出現問題  
“**<span style="color: #ff0000;">PHP Startup: Unable to load dynamic Library &#8216;\xampp\php\ext\php_mssql.dll&#8217; &#8211; The specified module could not be found</span>**”

如果你的Server 上在**PHP** 資料夾中沒有**<span style="color: #3366ff;">php_mssql.dll</span>**  
路徑 如: **<span style="color: #0000ff;">root directory\php\ext</span>** 資料夾中..沒有**<span style="color: #3366ff;">php_mssql.dll</span>**和你的**Apache**便會出現以下的錯誤信息&#8230;  
“**<span style="color: #ff0000;">PHP Startup: Unable to load dynamic Library &#8216;\xampp\php\ext\php_mssql.dll&#8217; &#8211; The specified module could not be found</span>**”  
[<img class="alignnone" title="PHP Startup: Unable to load dynamic Library '\xampp\php\ext\php_mssql.dll' - The specified module could not be found" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/15c04b9d07c34c6290a659e917bf9a6a/renditions/fullsize.jpg?resize=483%2C169" alt="" width="483" height="169" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/15c04b9d07c34c6290a659e917bf9a6a/renditions/fullsize.jpg)

**解決方法**:  
你可以到以下URL 下載** <span style="color: #3366ff;">php_mssql.dll<br /> </span>**  
 <a title="SkyDrive File for php_mssql.dll Download" href="https://skydrive.live.com/?cid=66398506b8d4b8bf&sc=documents&uc=2&id=66398506B8D4B8BF%21125#" target="_blank">https://skydrive.live.com/?cid=66398506b8d4b8bf&sc=documents&uc=2&id=66398506B8D4B8BF%21125#</a>  
之後打已下載 的**<span style="color: #3366ff;">php_mssql.dll</span>** 檔案放進php資料夾裡面的ext資料夾入面便可  
E.g, **<span style="color: #0000ff;">H:\xampp\php\ext\<br /> <a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a2780de065184c899a8af381f71a03f7/renditions/fullsize.jpg"><img class="alignnone" title="php/ext folder" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a2780de065184c899a8af381f71a03f7/renditions/fullsize.jpg?resize=596%2C412" alt="" width="596" height="412" data-recalc-dims="1" /></a> </span>**

之後停用**Apache/IIS Web Server**之後重新啟動便可以了

Hope you find it useful