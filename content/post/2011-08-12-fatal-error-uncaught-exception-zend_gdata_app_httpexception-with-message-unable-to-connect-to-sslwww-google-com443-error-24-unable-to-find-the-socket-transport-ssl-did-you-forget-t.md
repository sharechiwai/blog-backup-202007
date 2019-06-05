---
id: 1981
title: 'Fatal error: Uncaught exception &#8216;Zend_Gdata_App_HttpException&#8217; with message &#8216;Unable to Connect to ssl://www.google.com:443. Error #24: Unable to find the socket transport &#8220;ssl&#8221; &#8211; did you forget to enable it when you configured PHP?&#8217; in'
date: 2011-08-12T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1981
permalink: /2011/08/fatal-error-uncaught-exception-zend_gdata_app_httpexception-with-message-unable-to-connect-to-sslwww-google-com443-error-24-unable-to-find-the-socket-transport-ssl-did-you-forget-t/
categories:
  - PHP 新手筆記
tags:
  - Google Doc
  - XAMPP
  - Zend Framework
---
今日朋友幫我寫了一個sample page..用來取**Google Spreadsheet**的資料的..  
當我嘗試在我電腦上的**xampp**上執行時.. 出現了以下的錯誤信息:  
&#8220;**<span style="color: #ff0000;">Fatal error: Uncaught exception &#8216;Zend_Gdata_App_HttpException&#8217; with message &#8216;Unable to Connect to ssl://www.google.com:443. Error #24: Unable to find the socket transport &#8220;ssl&#8221; &#8211; did you forget to enable it when you configured PHP?&#8217; in</span>**&#8221;

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1edb48cb7bba4342961d050cbe97b883/renditions/fullsize.jpg?resize=606%2C79" alt="Fatal error: Uncaught exception 'Zend_Gdata_App_HttpException' with message 'Unable to Connect to ssl://www.google.com:443. Error #24: Unable to find the socket transport 'ssl'" width="606" height="79" data-recalc-dims="1" /> 

因為錯誤信息指是和**SSL** 有關的.. 所以我便用 **<span style="color: #008000;">phpino()</span>** 來檢查一下Apache/PHP Server的設定  
看到**Apache** 是支援**SSL** 的 “Apache2Ha**ndler &#8211; DAV/2 mod_ssl/2.2.11 OpenSSL/0.9.8i PHP/5.2.9**”  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cd1d0ee67d5346889406965c67148edb/renditions/fullsize.jpg?resize=625%2C106" alt="Apache SSL Handler" width="625" height="106" data-recalc-dims="1" />  
但是找不到**PHP** 有啟用了**SSL** 的設定..  
所以我便開啟了 **php.ini** 找出 “**<span style="color: #008000;">extension php_openssl.dll</span>**” 之後除去前面的&#8221;**<span style="color: #008000;">;</span>**&#8221; 便可以了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/06ee2beb61604434abe062b1db50ca39/renditions/fullsize.jpg?resize=300%2C128" alt="php.ini enable php_openssl.dll" width="300" height="128" data-recalc-dims="1" />  
儲存後 重新啟動**Apache** 之後再次執行 **phpinfo()** 便會看了 **OpenSSL** 啟用了  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/96ac0f46a76947d3810991d8ab953ac9/renditions/fullsize.jpg?resize=615%2C112" width="615" height="112" alt="php.ini OpenSSL Enabled" data-recalc-dims="1" /> 

當我再次執行朋友幫我寫的Sample page 也沒有再出再問題了

Hope you find it useful