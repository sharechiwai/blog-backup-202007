---
id: 1973
title: 'Apache &#8211; Internal Server Error &#8211; The server encountered an internal error or misconfiguration and was unable to complete your request. Apache/2.2.16 (Debian) Server at'
date: 2011-08-07T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1973
permalink: /2011/08/apache-internal-server-error-the-server-encountered-an-internal-error-or-misconfiguration-and-was-unable-to-complete-your-request-apache2-2-16-debian-server-at/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - .htaccess
  - Apache
  - Internal Server Error
  - url_rewrite
---
今天嘗試發佈我的網頁時出現 **Internal Server Error**了  
&#8220;<span style="color: #ff0000;"><strong>Internal Server Error</strong></span>

<span style="color: #ff0000;"><strong>The server encountered an internal error or misconfiguration and was unable to complete your request.</strong></span>

<span style="color: #ff0000;"><strong>Please contact the server administrator, [no address given] and inform them of the time the error occurred, and anything you might have done</strong></span>

<span style="color: #ff0000;"><strong>that may have caused the error.</strong></span>

<span style="color: #ff0000;"><strong>More information about this error may be available in the server error log.</strong></span>  
<span style="color: #ff0000;"><strong> Apache/2.2.16 (Debian) Server at sharechiwai.com Port 80</strong></span> &#8221;  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7f1b42cbe2e34bb29de1d08239a13c8f/renditions/fullsize.jpg?resize=625%2C352" alt="Internal Server Error" width="625" height="352" data-recalc-dims="1" />  
之前也有經驗遇到了差不多的問題&#8230;  
原因是因為 **.htaccess**檔案 用的**mod_rewrite** 在**apache**沒有啟用的關係所以出現的..  
或是因為沒有加上

<pre>&lt;IfModule mod_rewrite.c&gt;

&lt;/IfModule&gt;</pre>

造成的

我也檢查了**Apache**的 **Error Log** 說是  
&#8220;**<span style="color: #ff0000;">/public_html/.htaccess: without matching section</span>**&#8221;

但是在電腦上打開 .htaccess檔案..看來是正常的

E.G.

<pre>&lt;IfModule mod_rewrite.c&gt;
RewriteEngine on
RewriteCond $1 !^(index\.php)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L,QSA]
&lt;/IfModule&gt;</pre>

這次查核了很久也找不到原因..  
最後便找了朋友幫忙了..  
之後便解決這個問題&#8230;

**解決方法**:  
用了 **SSH**登入了Web Server  
之後用 **nano** [Linux 的 Text Editor]  
打開 這個 **.htaccess** 檔案..  
之後發現檔案的開頭有一些怪獸文字..  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/78db4ca366904c11b92737921deae2e6/renditions/fullsize.jpg?resize=625%2C206" alt=".htaccess file" width="625" height="206" data-recalc-dims="1" />  
把怪獸文字刪除之後儲存檔案便可以了

原因應該是我的文字的**encoding** 的問題..  
我是用**Windows**的 而**web server**是用 **Linux** 的

Hope you find it useful