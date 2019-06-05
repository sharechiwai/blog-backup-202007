---
id: 3090
title: 'Disable Directory Listing via .htaccess &#8211; 使用 .htaccess 隱藏目錄列表'
date: 2014-03-10T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3090
permalink: '/2014/03/disable-directory-listing-via-htaccess-%e4%bd%bf%e7%94%a8-htaccess-%e9%9a%b1%e8%97%8f%e7%9b%ae%e9%8c%84%e5%88%97%e8%a1%a8/'
categories:
  - Security/電腦保安
tags:
  - .htaccess
---
公司的 **Infrastructure Consultant** 常常對我們說..  
緊記如非必要..一定要停用**目錄列表 / Directory Listing**&#8230;  
令其他人/或程式不能容地開啟你網站上&#8230;不想隨意顯示給訪客看的檔案

**解決方法** 十分簡單

只要在網頁上的 **.htaccess**檔案上加上以下的程式碼便可以  
**<span style="color: #008000;"># disable directory listing</span>**  
** <span style="color: #008000;">Options -Indexes</span>**

<img class="alignnone" alt="Disable Directory Listing via .htaccess" src="https://i0.wp.com/farm3.staticflickr.com/2235/13078955003_6f6120bd7e_o.jpg?resize=297%2C66" width="297" height="66" data-recalc-dims="1" />  
Hope you find it useful