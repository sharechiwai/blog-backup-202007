---
id: 2544
title: 'How to enable GZip via .htaccess &#8211; 在.htaccess 檔案上Enable GZip'
date: 2012-08-15T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2544
permalink: '/2012/08/how-to-enable-gzip-via-htaccess-%e5%9c%a8-htaccess-%e6%aa%94%e6%a1%88%e4%b8%8aenable-gzip/'
categories:
  - Web Optimisation
tags:
  - Apache
  - gzip
  - XAMPP
---
在之前的一篇網誌上介紹了如何在**Apache** / **XAMPP**上啟用 **GZip Compression**.

# <a title="Permalink to Enable GZip Compression on Apache  XAMPP – 在Apache XAMPP 上 啟用 GZip 壓縮" href="http://blog.sharechiwai.com/2012/08/enable-gzip-compression-on-apache-xampp-%e5%9c%a8apache-xampp-%e4%b8%8a-%e5%95%9f%e7%94%a8-gzip-%e5%a3%93%e7%b8%ae/" rel="bookmark">Enable GZip Compression on Apache XAMPP – 在Apache XAMPP 上 啟用 GZip 壓縮</a>

原來在**Apache**上 Enable了 **GZip Compression Module** 之後  
也需要在Website中的&#8221;**.htaccess**&#8221;

以下是說給**Server**看這個網頁會使用**GZip** 來壓縮內容的script

[xml]

#檢查 如果 mod_deflate存在的話執行以下script  
<IfModule mod_deflate.c>

\# 啟動GZIP  
<IfModule mod_setenvif.c>  
<IfModule mod_headers.c>  
SetEnvIfNoCase ^(Accept-EncodXng|X-cept-Encoding|X{15}|~{15}|-{15})$ ^((gzip|deflate)\s\*,?\s\*)+|[X~-]{4,13}$ HAVE_Accept-Encoding  
RequestHeader append Accept-Encoding "gzip,deflate" env=HAVE_Accept-Encoding  
</IfModule>  
</IfModule>

\# 以下是上一個網誌中提到的Filter 功能  
#下列的設定是把以下MIME type 的檔案用GZIP處厘  
<IfModule mod_filter.c>  
AddOutputFilterByType DEFLATE application/atom+xml \  
application/javascript \  
application/json \  
application/rss+xml \  
application/vnd.ms-fontobject \  
application/x-font-ttf \  
application/xhtml+xml \  
application/xml \  
font/opentype \  
image/svg+xml \  
image/x-icon \  
text/css \  
text/html \  
text/plain \  
text/x-component \  
text/xml  
</IfModule>

</IfModule>  
[/xml]

Hope you find it useful