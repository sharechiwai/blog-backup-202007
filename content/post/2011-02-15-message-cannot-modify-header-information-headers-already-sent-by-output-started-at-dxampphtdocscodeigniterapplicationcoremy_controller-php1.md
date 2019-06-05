---
id: 1284
title: 'Message: Cannot modify header information &#8211; headers already sent by (output started at D:xampphtdocscodeigniterapplicationcoreMY_Controller.php:1)'
date: 2011-02-15T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1284
permalink: /2011/02/message-cannot-modify-header-information-headers-already-sent-by-output-started-at-dxampphtdocscodeigniterapplicationcoremy_controller-php1/
categories:
  - Codeingter
---
在使用**CodeIgniter**時 久不久便會出現這個問題&#8230;

[相信大家在使用 PHP 時也會有遇到差不多的問題的]  
[<img class="alignnone" title="Message: Cannot modify header information - headers already sent by (output started at D:xampphtdocscodeigniterapplicationcoreMY_Controller.php:1)" src="https://i0.wp.com/farm6.static.flickr.com/5097/5441338648_65d67b0d1e.jpg?resize=492%2C161" alt="Message: Cannot modify header information - headers already sent by (output started at D:xampphtdocscodeigniterapplicationcoreMY_Controller.php:1)" width="492" height="161" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5097/5441338648_65d67b0d1e.jpg)

&#8220;<span style="color: #ff0000;"><strong>A PHP Error was encountered<br /> Severity: Warning</strong></span>

<span style="color: #ff0000;"><strong>Message: Cannot modify header information &#8211; headers already sent by (output started at D:xampphtdocscodeigniterapplicationcoreMY_Controller.php:1)</strong></span>

<span style="color: #ff0000;"><strong>Filename: libraries/Session.php</strong></span>

<span style="color: #ff0000;"><strong>Line Number: 670</strong></span>&#8221;

**解決方法** 其實很簡單

大家只要檢查一下出現錯誤的file  
[E.g. 在我這個例子是 **MY_Controller.php**]

在 **PHP tag** 之前有沒有一些 字  
如果有的話請你刪除不必要的字

如果沒有的話&#8230; 可以嘗試另存你的檔案&#8230;  
E.G. **UTF-8 without BOM**

我的請況就是看不到任何多餘的字元..  
但是還是出現這個Error

最後我把檔案的**編碼/Encoding**由 **UTF8 轉為 UTF-8 without BOM**  
之後便解決了這個問題

原來的檔案編碼/Encoding

<div style="width: 437px" class="wp-caption alignnone">
  <a href="https://i2.wp.com/farm6.static.flickr.com/5099/5440734709_5c9420caa9.jpg"><img title="File Encoding UTF-8" src="https://i2.wp.com/farm6.static.flickr.com/5099/5440734709_5c9420caa9.jpg?resize=427%2C276" alt="" width="427" height="276" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    File Encoding UTF-8
  </p>
</div>

更改後的 檔案編碼/Encoding  
[<img class="alignnone" title="UTF-8 without BOM" src="https://i0.wp.com/farm6.static.flickr.com/5297/5441338732_af5ec903b4.jpg?resize=423%2C278" alt="UTF-8 without BOM" width="423" height="278" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5297/5441338732_af5ec903b4.jpg)

Hope you find it useful