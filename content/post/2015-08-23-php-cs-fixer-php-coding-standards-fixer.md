---
id: 3477
title: 'PHP-cs-fixer &#8211; PHP Coding Standards Fixer'
date: 2015-08-23T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3477
permalink: /2015/08/php-cs-fixer-php-coding-standards-fixer/
categories:
  - PHP 新手筆記
tags:
  - Best Practices
  - Coding Standard
  - PHP
  - PHP-CS-FIXER
  - XAMPP
---
自從用了 **Visual Studio**的 **StyleCop** / **Resharper**  
之後便開始愛上**Coding Standard** / **Best Practice**..  
因為這些**Coding Standard** 的工具可以幫助我們寫一些更有效率的程式碼  
還有..如果所有**Developer** 都跟隨著這些**Coding Standard**..  
便其他人便可以很容易便明白程式是怎樣 layout的

最近開始寫多了**PHP** 相關的網站..  
如果有一些免費的工具..像**StyleCop** 或  
朋友便介紹..我可以使用**PHP-CS-FIXER** 來做差不多的東西..  
你可以使用**PHP Command** 來執行**PHP-CS-FIXER**

首先我們先要以下網址去下載**php-cs-fixer.phar  
<a href="https://github.com/FriendsOfPHP/PHP-CS-Fixer" target="_blank">https://github.com/FriendsOfPHP/PHP-CS-Fixer</a>**  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3772/20363513662_cbfc643921_z.jpg?resize=625%2C386" alt="Download PHP-CS-FIXER" width="625" height="386" data-recalc-dims="1" />  
之後把他儲存在 一個容易找到的位置..因為我們要用這個路徑來執行**php-cs-fixer** 的  
我便把他儲存在&#8221;<span style="color: #008000;"><strong>d:\xampp\php\extras\php-cs-fixer.phar</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/419/20184045088_90acd9d9cb_z.jpg?resize=564%2C277" alt="PHP-CS-Fixer.phar Location" width="564" height="277" data-recalc-dims="1" /> 

所有東西都準備好之後我們便可以嘗試執行 **php-cs-fixer** 了  
**執行方法** 是這樣的

<span style="text-decoration: underline;"><span style="color: #008000; text-decoration: underline;"><a style="color: #008000; text-decoration: underline;" href="http://farm1.static.flickr.com/419/20184045088_90acd9d9cb_z.jpg"><strong>php</strong> [Full file path for <strong>php-cs-fixer.phar</strong> e.g. d:\xampp\php\extras\php-cs-fixer.phar] fix [<strong>PHP code folder path</strong> e.g. d:\xampp\htdocs\sharechiwai\applicat</a></span></span>  
<span style="text-decoration: underline;"><span style="color: #008000; text-decoration: underline;"><a style="color: #008000; text-decoration: underline;" href="http://farm1.static.flickr.com/419/20184045088_90acd9d9cb_z.jpg"> ion\controllers]<strong> &#8211;fixers=[settings e.g. -indentation]</strong></a></span></span>

<pre>php php-cs-fixer.phar fix D:\xampp\htdocs\BlogBackup\wp-content --fixers=-indentation
</pre>

結果像這樣  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/457/20504680762_f1d6cd9c68_z.jpg?resize=625%2C313" alt="PHP-CS-Fixer Result" width="625" height="313" data-recalc-dims="1" />  
完成後會總結那些檔案更新了..和那些檔案有問題..  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/566/20326817189_fea5014c1b_z.jpg?resize=625%2C314" alt="PHP-CS-Fixer Summary" width="625" height="314" data-recalc-dims="1" /> 

更多怎樣使用 **php-cs-fixer** 指令和變數的 詳情可以參考下以網址  
<a href="http://cs.sensiolabs.org/" target="_blank">http://cs.sensiolabs.org/</a>  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/342/19890866584_76e8e1ccc2_z.jpg?resize=625%2C380" alt="PHP-CS-Fixer Variable / Parameters" width="625" height="380" data-recalc-dims="1" /> 

Hope you find it useful