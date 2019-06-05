---
id: 3448
title: 'Codeigniter GoDaddy .htaccess URL Rewrite issue &#8211; Codeigniter 在GoDaddy 網站寄存上 .htaccess Url Rewrite 的問題'
date: 2015-08-01T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3448
permalink: '/2015/08/codeigniter-godaddy-htaccess-url-rewrite-issue-codeigniter-%e5%9c%a8godaddy-%e7%b6%b2%e7%ab%99%e5%af%84%e5%ad%98%e4%b8%8a-htaccess-url-rewrite-%e7%9a%84%e5%95%8f%e9%a1%8c/'
categories:
  - Codeingter
tags:
  - .htaccess
  - Codeigniter
  - GoDaddy
  - PHP Troubleshooting
  - url_rewrite
---
今日再Upload一個Dev的網頁到 **GoDaddy** Hosting時  
不知道為什麼只是可以看到主頁..  
e.g. <a href="http://sharechiwai.com" target="_blank">http://sharechiwai.com</a>  
但是當我嘗試到 其他頁時  
E.G.  
<a href="http://sharechiwai.com/app/youtubedownload" target="_blank">http://sharechiwai.com/app/youtubedownload</a>  
便出現以下的錯誤  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/314/19633761963_10cbcbf4ec_z.jpg?resize=476%2C425" alt="500 Internal Server Error - due to wrong URL Rewrite rules on .htaccess" width="476" height="425" data-recalc-dims="1" /> 

如何在 **Codeigniter**上使用 **.htaccess**的 **URL rewrite** 去**隱藏 index.php**  
之前介紹過  
<a href="http://blog.sharechiwai.com/2010/11/codeigniter-to-remove-index-php-url-%e5%9c%a8codeigniter-%e7%9a%84url-%e4%b8%ad-%e9%99%a4%e5%8e%bbindex-php/" target="_blank">Codeigniter to remove index.php URL – 在Codeigniter 的URL 除去index.php</a>  
E.G.

<pre>RewriteEngine on
RewriteCond $1 !^(index.php)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L,QSA]
</pre>

在**Microsoft Azure** 自己設定的 **Ubuntu** 上沒有問題  
但是在**GoDaddy**上出現問題

做了一會research之後終於找到了解決方法  
**GoDaddy**的**.htaccess**的 **URL Rewrite rule**有小小不同的

我們可以使用以下的 **URL rewrite rules** 去解決 **Codeigniter** 在**GoDaddy** 網站寄存上 **.htaccess Url Rewrite** 的問題

<pre>RewriteEngine on
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ /index.php?$1 [L]
</pre>

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/530/19633761953_ce856e1a88_z.jpg?resize=472%2C392" alt="Codeigniter GoDaddy URL Rewrite Issue fixed" width="472" height="392" data-recalc-dims="1" />  
Hope you find it useful