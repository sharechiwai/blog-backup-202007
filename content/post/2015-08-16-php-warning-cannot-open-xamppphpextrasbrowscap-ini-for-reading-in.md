---
id: 3470
title: 'PHP Warning:  Cannot open &#8216;\xampp\php\extras\browscap.ini&#8217; for reading in'
date: 2015-08-16T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3470
permalink: /2015/08/php-warning-cannot-open-xamppphpextrasbrowscap-ini-for-reading-in/
categories:
  - PHP 新手筆記
tags:
  - PHP
  - PHP Troubleshooting
  - XAMPP
---
之前介紹過怎樣在**Windows** 執行 **PHP Command** E.G. **設定環境變數**  
和怎樣解決 **PHP Unable to load dynamic library** 的問題

到最後我們還有另一個問題要解決..  
就是  
&#8220;**<span style="color: #ff0000;">PHP Warning: Cannot open &#8216;\xampp\php\extras\browscap.ini&#8217; for reading in Unknown on line 0</span>**&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/261/20155284838_249332e932_z.jpg?resize=625%2C207" alt="PHP Warning:  Cannot open '\xampp\php\extras\browscap.ini' for reading in Unknown on line 0" width="625" height="207" data-recalc-dims="1" /> 

問題出現的原因和之前的一樣..是一個**路徑**計定的問題

**解決方法**十分簡單  
我們可以開啟 **php.ini** 檔案.. 之後  
**browscap** 的 路徑  
由

<pre>browcap = "\xampp\php\extras\browscap.ini"
</pre>

<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/522/20317059316_5530d370ca_z.jpg?resize=544%2C281" alt="browscap path on php.ini" width="544" height="281" data-recalc-dims="1" /> 

轉為

<pre>browcap = "d:\xampp\php\extras\browscap.ini"
</pre>

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/361/20178424318_ab25a6ef30_z.jpg?resize=543%2C363" alt="Cannot load browscap xampp php.ini fixed" width="543" height="363" data-recalc-dims="1" /> 

之後再嘗試一下.. **browscap** 的問題應該解決了

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/426/20334825372_cbe694f479_z.jpg?resize=582%2C136" alt="PHP Command Successfully set up on Windows machine" width="582" height="136" data-recalc-dims="1" /> 

Hope you find it useful