---
id: 3462
title: '&#8216;php&#8217; is not recognized as an internal or external command &#8211; How to run PHP Command Line on Windows &#8211; 怎樣在Windows 上執行php 指令'
date: 2015-08-10T00:00:20+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3462
permalink: '/2015/08/php-is-not-recognized-as-an-internal-or-external-command-how-to-run-php-command-line-on-windows-%e6%80%8e%e6%a8%a3%e5%9c%a8windows-%e4%b8%8a%e5%9f%b7%e8%a1%8cphp-%e6%8c%87%e4%bb%a4/'
categories:
  - PHP 新手筆記
tags:
  - PHP Troubleshooting
  - XAMPP
---
最近用多了**PHP** 的**Library**..  
很多時候都需要以**PHP Command** 來執行的  
當我在Command Prompt 上輸入 php之後執行時 出現了以下錯誤  
&#8220;&#8216;php&#8217; is not recognized as an internal or external command, operable program or batch file.&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/383/20155465159_d354bc35fe_z.jpg?resize=568%2C112" alt="PHP is not recognized as an internal or external command, operable program or batch file" width="568" height="112" data-recalc-dims="1" /> 

在**Command Prompt** 上執行 **PHP 指令**其實很容易的  
在**Windows** 上我們只需要把 **php.exe** 的資料夾 **註冊在 Windows 的 Environment Variable** /**環境變數** 便可以

首先要找到我們的**PHP.exe** 儲存在那裡  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/297/20154040660_47376974ed_z.jpg?resize=593%2C178" alt="XAMPP PHP Folder" width="593" height="178" data-recalc-dims="1" />  
由於我是使用**xampp**的所以我的 **php.exe** 會存在  
<span style="color: #008000;"><strong>[xampp 的儲存路徑]\php\</strong></span>

<span style="color: #000000;">“<strong>Advanced System Settings/進階系統設定</strong>” -> “<strong>Advanced tab/進階 分頁</strong>” ->”<strong>Environment Variables / 環境變數</strong>” 按一下</span>  
<span style="color: #000000;">在之前的網誌有介紹如何修改”<strong>Environment Variables</strong> / <strong>環境變數</strong>” 有興趣的朋友可以到以下網誌參考</span>**  
<a href="http://blog.sharechiwai.com/2014/07/how-to-install-ant-on-windows-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e4%b8%8a%e5%ae%89%e8%a3%9dant/" rel="bookmark">How to install Ant on Windows – 如何在Windows 上安裝Ant<br /> </a>**  
<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/372/19721128173_bd0a4e3087_z.jpg?resize=625%2C473" alt="Environment Variable" width="625" height="473" data-recalc-dims="1" />  
儲存之後按 &#8220;**OK**/**確定**&#8221;  
之後再**登出再登入Windows** 便可

<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/414/19719455484_e0f2f255c0_z.jpg?resize=625%2C128" alt="Execute PHP on Windows Command Prompt" width="625" height="128" data-recalc-dims="1" />  
我的**PHP config** 檔案出現了小小問題..之後的網誌會介紹怎樣解決這些1

Hope you find it useful