---
id: 3654
title: 'HTTP Error 404.3 &#8211; Not Found The page you are requesting cannot be served because of the extension configuration. If the page is a script, add a handler. If the file should be downloaded, add a MIME map.'
date: 2016-05-07T00:00:43+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3654
permalink: /2016/05/http-error-404-3-not-found-the-page-you-are-requesting-cannot-be-served-because-of-the-extension-configuration-if-the-page-is-a-script-add-a-handler-if-the-file-should-be-downloaded-add-a-mime-m-2/
categories:
  - ASP.Net MVC
tags:
  - ASP.Net
  - ASP.Net MVC
  - ASP.Net Troubleshooting
---
Freelance的那個 **ASP.Net MVC 5** Project 上加了一些新的 **CSS** 檔案..  
當中有一些 **CSS** 檔是reference 了到一些 Font 既檔案上 &#8220;**.woff2**&#8221;  
誰不知 Default的 **ASP.Net MVC** 沒有**config**可以 serve 這個file extension  
所以嘗網頁嘗試 Load 這個 file 是便出現<span style="color: #ff0000;"><strong> HTTP 404.3 Not Found</strong></span>了

&#8220;<span style="color: #ff0000;"><strong>HTTP Error 404.3 &#8211; Not Found The page you are requesting cannot be served because of the extension configuration. If the page is a script, add a handler. If the file should be downloaded, add a MIME map</strong></span>.&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7538/26575892300_404fa80918_z.jpg?resize=625%2C396" alt="HTTP Error 404.3 - Not Found The page you are requesting cannot be served because of the extension configuration. If the page is a script, add a handler. If the file should be downloaded, add a MIME map." width="625" height="396" data-recalc-dims="1" /> 

**解決方法**十分簡單  
我們只需要在**Web.config**上 加上容許那些**MIME** 檔案 **extension**便可以了

<pre>  &lt;system.webServer&gt;
 &lt;staticContent&gt;
 &lt;mimeMap fileExtension=".woff2" mimeType="application/font-woff2" /&gt;
 &lt;/staticContent&gt;
 &lt;/system.webServer&gt;</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7525/26244347353_3c89781708_z.jpg?resize=625%2C87" alt="Web.config add supported MIME type" width="625" height="87" data-recalc-dims="1" />  
Hope you find it useful