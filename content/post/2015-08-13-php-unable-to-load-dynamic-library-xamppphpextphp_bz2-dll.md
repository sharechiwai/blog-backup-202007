---
id: 3465
title: 'PHP Unable to load dynamic library &#8216;\xampp\php\ext\php_bz2.dll&#8217;'
date: 2015-08-13T22:35:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3465
permalink: /2015/08/php-unable-to-load-dynamic-library-xamppphpextphp_bz2-dll/
categories:
  - PHP 新手筆記
tags:
  - PHP Troubleshooting
  - XAMPP
---
當我嘗試在Command Prompt上執行 php的指令時..出現以下的錯誤  
&#8220;<span style="color: #ff0000;"><strong>PHP Warning: PHP Startup: Unable to load dynamic library &#8216;\xampp\php\ext\php_bz2.dll</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/432/19720663114_d9c2d32f34_z.jpg?resize=562%2C272" alt="PHP Startup: Unable to load dynamic library php_bz2.dll" width="562" height="272" data-recalc-dims="1" /> 

&#8220;<span style="color: #ff0000;"><strong>PHP Warning: PHP Startup: Unable to load dynamic library &#8216;\xampp\php\ext\php_curl.dll</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/337/20343320235_2dedd0a4b0_z.jpg?resize=625%2C299" alt="PHP Startup: Unable to load dynamic library php_curl.dll" width="625" height="299" data-recalc-dims="1" /> 

還有很多其他的**Dynamic Library**  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/452/19720663504_08b686d048_z.jpg?resize=421%2C640" alt="PHP unable to load dynamic library" width="421" height="640" data-recalc-dims="1" /> 

<pre>PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_bz2.dll

Warning: PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_bz2.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_curl.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_mbstring.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_exif.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_gd2.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_gettext.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_mysql.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_mysqli.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_openssl.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_pdo_mysql.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_pdo_sqlite.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_soap.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_sockets.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_sqlite3.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_xmlrpc.dll

PHP Warning:  PHP Startup: Unable to load dynamic library '\xampp\php\ext\php_xsl.dll

PHP Warning:  Cannot open '\xampp\php\extras\browscap.ini' for reading in Unknown on line 0
</pre>

之後去查看了 **php/ext** 資料來..  
[由于我是使用 **xampp** 的關係..我的**xampp** 資料夾是儲存在**d:\**  
所以我的 **xampp path** 是這樣的 **D:\xampp\php\ext\**]

發現上面說明&#8217;**Unable to load**&#8216; 的 **Dynamic Library** 都可以在這裡找到  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3743/20349384541_8acf370745_z.jpg?resize=625%2C292" alt="PHP Ext Folder in XAMPP" width="625" height="292" data-recalc-dims="1" /> 

所以應該不是**Library**的問題  
而是<span style="color: #0000ff;"><strong>php.ini</strong></span> 內的一些設定問題

做了一會research 之後發現

**解決方法**十分簡單  
只要將預設的 <span style="color: #008000;"><strong>extension_dir</strong> </span>設定變成我們的 **absolute path**便可以  
**E.G. D:\xampp\php\ext\**  
將

<pre>extension_dir = "\xampp\php\ext"
</pre>

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/290/20343320415_780d263a50_z.jpg?resize=539%2C354" alt="php.ini extension_dir" width="539" height="354" data-recalc-dims="1" />  
轉成

<pre>extension_dir = "d:\xampp\php\ext"
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3775/20155284688_74b8698b7a_z.jpg?resize=530%2C344" alt="php.ini extension_dir with absolute path" width="530" height="344" data-recalc-dims="1" /> 

之後問題便可以**解決**了  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/426/20334825372_cbe694f479_z.jpg?resize=582%2C136" alt="PHP command works" width="582" height="136" data-recalc-dims="1" /> 

Hope you find it useful