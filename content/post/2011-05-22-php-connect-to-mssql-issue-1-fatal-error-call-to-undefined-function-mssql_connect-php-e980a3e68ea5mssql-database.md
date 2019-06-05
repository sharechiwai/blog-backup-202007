---
id: 1835
title: 'PHP Connect to MSSQL Issue 1 &#8211; Fatal error: Call to undefined function mssql_connect()  &#8211; PHP 連接MSSQL Database'
date: 2011-05-22T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1835
permalink: '/2011/05/php-connect-to-mssql-issue-1-fatal-error-call-to-undefined-function-mssql_connect-php-%e9%80%a3%e6%8e%a5mssql-database/'
categories:
  - PHP 新手筆記
tags:
  - MSSQL
  - PHP
  - XAMPP
---
今日有朋友找我一起研究用**PHP** 連接到**MSSQL server**..  
通常**PHP**多會使用**MySQL Server** 為**Backend Database**的..

所以我們希望練習一下用**MSSQL 做Backend Database**  
試試有沒有問題&#8230;

答案是有問題的&#8230;  
原來不是那麼簡單的&#8230;

以下是一些測試的程式碼

[php]  
$conn = mssql_connect($ServerName, $DBUsername, $DBPassword)  
or die("Couldn&#8217;t connect to SQL Server on $myServer");

if (!$conn) {  
die(&#8216;Something went wrong while connecting to MSSQL&#8217;);  
}  
[/php]

我們會用到<span style="color: #339966;"><strong>mssql_connect </strong></span>這個method

當我嘗試使用這個測試的程式碼時便出現下面的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Fatal error: Call to undefined function mssql_connect() in H:\xampp\htdocs\sql.php on line 23</strong></span>&#8221;  
[<img class="alignnone" title="Fatal error: Call to undefined function mssql_connect() in H:\xampp\htdocs\sql.php on line 23" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/edaa7ffd435c4cd9a58051c2f2829c56/renditions/fullsize.jpg?resize=625%2C79" alt="" width="625" height="79" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/edaa7ffd435c4cd9a58051c2f2829c56/renditions/fullsize.jpg)

**解決方法**十分簡單  
只要打開<span style="color: #3366ff;"><strong>php.ini</strong></span>  
[<img class="alignnone" title="PHP.ini File" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e25dcf2fcca04f7ea39e21498c1ca24e/renditions/fullsize.jpg?resize=570%2C336" alt="" width="570" height="336" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e25dcf2fcca04f7ea39e21498c1ca24e/renditions/fullsize.jpg)

找到 **<span style="color: #339966;">;extension=php_mssql.dll</span>**  
打**extension=php_mssql.dll** 前面的 &#8220;**<span style="color: #339966;">;</span>**&#8221; 刪除便可以了  
之後需要重新啟動**Web Server** E.g. **Apache/IIS  
[<img class="alignnone" title="extension=php_mssql.dll" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8c4193e4b5e64f9fb0c9fcad1b1eba9a/renditions/fullsize.jpg?resize=334%2C72" alt="" width="334" height="72" data-recalc-dims="1" />](https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8c4193e4b5e64f9fb0c9fcad1b1eba9a/renditions/fullsize.jpg)**  
如果你的**Server** 上在**PHP** 資料夾中沒有**<span style="color: #3366ff;">php_mssql.dll</span>**  
路徑 如:** <span style="color: #0000ff;">root directory\php\ext</span>** 資料夾中..沒有php_mssql.dll和你的Apache便會出現以下的錯誤信息&#8230;  
“**<span style="color: #ff0000;">PHP Startup: Unable to load dynamic Library &#8216;\xampp\php\ext\php_mssql.dll&#8217; &#8211; The specified module could not be found</span>**”  
[<img class="alignnone" title="PHP Startup: Unable to load dynamic Library '\xampp\php\ext\php_mssql.dll' - The specified module could not be found" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/15c04b9d07c34c6290a659e917bf9a6a/renditions/fullsize.jpg?resize=483%2C169" alt="" width="483" height="169" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/15c04b9d07c34c6290a659e917bf9a6a/renditions/fullsize.jpg)

**解決方法**:  
可以參考以下教學:  
<a title="PHP Connect to MSSQL Issue 1 Part2 – PHP Startup: Unable to load dynamic Library ‘\xampp\php\ext\php_mssql.dll’ – The specified module could not be found PHP 連接MSSQL Database 問題" href="http://blog.sharechiwai.com/2011/05/php-connect-to-mssql-issue-1-part2-php-startup-unable-to-load-dynamic-library-xamppphpextphp_mssql-dll-the-specified-module-could-not-be-found-php-%E9%80%A3%E6%8E%A5mssql-database/" target="_blank">PHP Connect to MSSQL Issue 1 Part2 – PHP Startup: Unable to load dynamic Library ‘\xampp\php\ext\php_mssql.dll’ – The specified module could not be found PHP 連接MSSQL Database 問題</a>

Hope you find it useful