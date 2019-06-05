---
id: 3611
title: 'Message: file_get_contents(): Unable to find the wrapper &#8220;https&#8221; &#8211; did you forget to enable it when you configured PHP?'
date: 2016-04-01T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3611
permalink: /2016/04/message-file_get_contents-unable-to-find-the-wrapper-https-did-you-forget-to-enable-it-when-you-configured-php/
categories:
  - PHP 新手筆記
tags:
  - XAMPP
---
更新完 **XAMPP** 之後..當我嘗試執行 一個**Google API**的時候出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Message: file_get_contents(): Unable to find the wrapper &#8220;https&#8221; &#8211; did you forget to enable it when you configured PHP?</strong></span>&#8221;

原因是這個**API** 是用了 **HTTPS**  
而因為我的**Apache** / **PHP Web server**上沒有 **enable HTTPS wrapper []**

**解決方法**  
在**php.ini** 上 Enable **php_openssl** 這個**Module** 便可以了

by removing the &#8220;<span style="color: #339966;"><strong>;</strong></span>&#8221;

<pre>extension=php_openssl.dll
</pre>

Hope you find it useful