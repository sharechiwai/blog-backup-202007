---
id: 2542
title: 'Enable GZip Compression on Apache  XAMPP &#8211; 在Apache XAMPP 上 啟用 GZip 壓縮'
date: 2012-08-13T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2542
permalink: '/2012/08/enable-gzip-compression-on-apache-xampp-%e5%9c%a8apache-xampp-%e4%b8%8a-%e5%95%9f%e7%94%a8-gzip-%e5%a3%93%e7%b8%ae/'
categories:
  - Web Optimisation
tags:
  - Apache
  - gzip
  - XAMPP
---
最近都常常留意如何令到**網頁載入得更快**  
看了一些文章說如果先把網頁內容**GZip** 壓縮了便可以減小Bandwidth的使用了  
令到網頁載入得更快

如果大家是使用**Apache** 或 **XAMPP**的話可以嘗試以下的方法

**解法方法**  
開啟你的**Apache** / **XAMPP** 的 **Apache** 資料夾  
E.g. &#8220;<span style="color: #339966;"><strong>D:\xampp\apache</strong></span>\&#8221;  
之後開啟 &#8220;**Conf**&#8221; 資料夾..這個資料夾內儲有和**Apache Web Server**相關的配置資料的檔案  
E.G. &#8220;<span style="color: #339966;"><strong>D:\xampp\apache\conf\</strong></span>&#8221;  
打開&#8221;**httpd.conf**&#8221; 檔案  
之後 嘗試找出這一個module  
&#8220;**LoadModule deflate\_module modules/mod\_deflate.so**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a80c22e1a48548d1bd5d7ffb4cd84a4a" alt="mod_deflate" width="483" height="69" />  
和  
&#8220;**LoadModule filter\_module modules/mod\_filter.so**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1341432686294123bc0f9a3263665333" alt="mod_filter" width="468" height="99" />  
**mod_filter**是一個令**Apache**可以啟動過濾檔案功能的元件&#8230;  
啟用了他之後便可以specific那些檔案會Apply 那些功能等等&#8230;

刪除前面的 &#8220;**#**&#8221; 字串..把他uncomment  
之後重新啟動**Apache Web Server**便可以了

Hope you find it useful