---
id: 3472
title: 'Set up Composer with XAMPP &#8211; 如何在Windows XAMPP 上安裝 Composer &#8211; PHP Package Mangement Tool'
date: 2015-08-30T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3472
permalink: '/2015/08/set-up-composer-with-xampp-%e5%a6%82%e4%bd%95%e5%9c%a8windows-xampp-%e4%b8%8a%e5%ae%89%e8%a3%9d-composer-php-package-mangement-tool/'
categories:
  - PHP 新手筆記
tags:
  - Best Practices
  - Composer
  - Dependency Manager
  - Package Manager
  - PHP
  - XAMPP
---
朋友常常介紹我使用**Composer** 一個 **PHP 的 Package Management Tool  
Composer &#8211; Dependency Manager for PHP**  
十分有用..就像 **Visual Studio**的 **Nuget**和 **NodeJs** 的 **npm**  
有興趣既朋友可以參考以下網頁  
<a href="https://getcomposer.org/" target="_blank">https://getcomposer.org/</a>

<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/259/20367561445_a7c6c1c139_z.jpg?resize=577%2C640" alt="Composer - Dependency Manager for PHP" width="577" height="640" data-recalc-dims="1" /> 

今天想和大家分享怎樣在**Windows** 使用 **XAMPP** 的環境下安裝 **Composer**

安裝程序很簡單..但是我也曾經遇過些少問題..  
所以還是在這裡寫下些筆記吧.

首先大家需要到**Composer** 的網站 找**Windows Installer** 的 **Section** 下載<span style="color: #008000;"><strong>Composer_Setup.exe</strong></span>  
<a href="https://getcomposer.org/download/" target="_blank">https://getcomposer.org/download/</a>

之後開啟這檔案便可以開始安裝了 按&#8221;**Next** / **下一步**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/550/20180903519_0b4767c7eb_z.jpg?resize=518%2C407" alt="Composer Setup" width="518" height="407" data-recalc-dims="1" /> 

選擇安裝那些**Components**..我選擇了預設的選項  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/387/19746630713_9bc9427109_z.jpg?resize=526%2C402" alt="Composer Setup - Select Components" width="526" height="402" data-recalc-dims="1" /> 

按&#8221;**Next** / **下一步**&#8221; 之後需要選擇電腦上的 **PHP.exe** 的儲存位置[因為**Composer**需要使用**PHP**的]  
我是使用 **XAMPP** 的..所以我的**PHP** 是儲存在 **D:\xampp\php\php.exe**  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/308/19745019444_94423358ac_z.jpg?resize=519%2C404" alt="Composer select php.exe path" width="519" height="404" data-recalc-dims="1" /> 

按&#8221;**Next** / **下一步**&#8220;之後便會出現一個安裝前的總結..  
如果看了覺得設定沒有問題的話便可以按&#8221;**Install** / **安裝**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/381/20341305296_5ea9a0fcdc_z.jpg?resize=524%2C396" alt="Composer Setup Summary" width="524" height="396" data-recalc-dims="1" /> 

**安裝完成**  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/346/19744876624_49f2ff34bb_z.jpg?resize=518%2C400" alt="Completing Composer Setup" width="518" height="400" data-recalc-dims="1" /> 

登出再登入電腦之後便可以在**Command prompt** 上執行 **Composer**了  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/484/19744876614_45f552ab88_z.jpg?resize=625%2C310" alt="Composer install successfully" width="625" height="310" data-recalc-dims="1" /> 

Hope you find it useful