---
id: 3229
title: 'View Log on Openshift &#8211; 如何檢視Openshift 上的Log'
date: 2014-06-12T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3229
permalink: '/2014/06/view-log-on-openshift-%e5%a6%82%e4%bd%95%e6%aa%a2%e8%a6%96openshift-%e4%b8%8a%e7%9a%84log/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Apache
  - Openshift
  - PHP
---
最近使用了**Openshift**來寄存我在電腦活動的Project

由于這個**Project**是的Source Code是會和其他人分享的關係  
所以便使用一些較Standard的Code了  
為免令大家混淆&#8230;

我的Website 是用**PHP** 的**Codeigniter framework** 來寫的..  
在電腦活動時用了我自己原有的網頁來暫時建立一頁出來  
E.g.  
<a title="Share ChiWai - My Web Site" href="http://sharechiwai.com" target="_blank">http://sharechiwai.com</a>

所以把程式碼轉到新的**Project**上應該不太難..  
只要下載**Codeigniter**最新的檔案..之後再把和這個**Project**相關的程式碼由自己的網頁上抽出來便和更新一些變數便可以..

完成後**Commit** 到**Openshift**上也很順利..  
但是不知道為什麼某些頁面會出現

試過更新很多的程式碼和設定也是出現 &#8220;<span style="color: #ff0000;"><strong>500 Internal Server Error</strong></span>&#8221;

最後朋友建議看看Server 上的 Application Log 看看有沒有一些有用的資訊&#8230;  
我其實只是一個Linux 的初哥&#8230;所以要去查自一些Server的東西真是一點挑戰..  
做了一會Research 後找到了 如何檢視Openshift 上的Log

解決方法.  
首先以SSH 登入你的Openshift Account  
之後  
在**Command Prompt** 上輸入以下指令 去 **Log** 的資料夾上  
&#8220;<span style="color: #008000;"><strong>cd $OPENSHIFT_LOG_DIR</strong></span>&#8221;  
或  
&#8220;<span style="color: #008000;"><strong>cd /app-root/logs</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2927/14678661846_e45ac15c7b_z.jpg?resize=625%2C102" alt="OpenShift Access Log Folder" width="625" height="102" data-recalc-dims="1" /> 

之後輸入 &#8220;<span style="color: #008000;"><strong>ls</strong></span>&#8221; 去看看這個資料夾內有什麼log 我們可以參考  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5553/14701385742_2f9354f8ff_z.jpg?resize=625%2C102" alt="List Directory on the logs folder" width="625" height="102" data-recalc-dims="1" /> 

之後便可以使用**VIM**或**Nano** 來開啟這些**Log** 了  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5553/14678661916_751dbac258_z.jpg?resize=625%2C330" alt="View PHP Log on OpenShift Linux" width="625" height="330" data-recalc-dims="1" /> 

最後發現原來我的**Codeigniter Controller** 出現問題[太舊了..和新版的**Codeigniter**不太夾]

更新了那個**Controller** 之後再**Commit**我的程式碼便解決了

Hope you find it useful