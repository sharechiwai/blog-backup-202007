---
id: 2178
title: 'FileZilla show hidden file &#8211; 用FileZilla 顯示已隱藏的檔案'
date: 2011-11-09T00:00:41+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2178
permalink: '/2011/11/filezilla-show-hidden-file-%e7%94%a8filezilla-%e9%a1%af%e7%a4%ba%e5%b7%b2%e9%9a%b1%e8%97%8f%e7%9a%84%e6%aa%94%e6%a1%88/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Filezilla
  - FTP Client
---
今天又繼續開始更新的我網頁了&#8230;  
因為上星期我的**Hard Drive**壞掉了的關係&#8230;所以我所有的程式碼都不見了&#8230;  
不幸中的大幸是我的網頁是以**PHP**來寫的..  
所以我可以從**FTP**上找回我的網頁的檔案之後便可以繼續修改/加新的東西了  
如果是用**ASP.net** 寫的話..  
即使我可以去到**FTP** 找到發佈的資料夾..也不可以把他變回程式碼&#8230;

當我嘗試連接到**FTP** 時發現到一個小小的問題..  
就是我看不到我的&#8221;**.htaccess**&#8221; 檔案..  
相信是Server為了安全的關係..  
在**FTP Client [Filezilla]** 上隱藏了&#8221;**.htaccess**&#8221; 檔案&#8230;

由於我的網頁在 .**htaccess** 檔案上 放了一些 **url rewrite**的程式碼..  
所以沒有這個檔案我的網頁便不能正常運作了)

我又找不到在**Filezilla** 上怎樣可以顯示已隱藏的檔案  
最後做了一會學research 之後&#8230;終於找到了

解決方法十分簡單  
在**FileZilla**的&#8221;**工具列**&#8220;上 選擇 &#8220;**Server**&#8221; ->之後選取 &#8220;**Force showing hidden files**&#8221; 便可以  
<img alt="FileZilla force showing hidden files" src="https://i2.wp.com/farm4.staticflickr.com/3127/13078838055_5e406fccd2_o.jpg?w=625" data-recalc-dims="1" />  
之後**FileZilla**會彈出一個警告的信息  
<img alt="filezilla warning message" src="https://i0.wp.com/farm8.staticflickr.com/7330/13078836545_559a2da707_o.jpg?w=625" data-recalc-dims="1" />  
按一下&#8221;**OK**&#8221; 便可以了

Hope you find it useful