---
id: 3086
title: unable to locate package linux / Ubuntu
date: 2014-03-12T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3086
permalink: /2014/03/unable-to-locate-package-linux-ubuntu/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Ubuntu
---
今天嘗試在**Ubuntu**安裝一些程式/元件時  
出現了下面的錯誤  
&#8220;<span style="color: #ff0000;"><strong>unable to locate package</strong></span>&#8221;  
<img class="alignnone" alt="Unable to locate package" src="https://i2.wp.com/farm4.staticflickr.com/3175/13030593575_91cf674fdf_d.jpg?resize=500%2C324" width="500" height="324" data-recalc-dims="1" /> 

做了一會research 之後發現..  
應該是我這個**Ubuntu** / **Linux** 上的 **package list** 不夠Update  
所以便找不到了

**解決方法**..  
只要在**Terminal** 上先執行以下的指令便可以了

**<span style="color: #008000;">&#8220;sudo apt-get update&#8221;</span>**  
<img class="alignnone" alt="Ubuntu updating package list from repository" src="https://i0.wp.com/farm4.staticflickr.com/3293/13030974654_f38477f27e.jpg?resize=500%2C321" width="500" height="321" data-recalc-dims="1" /> 

執行後..從**Repositories** 上更新**Package List**  
<img class="alignnone" alt="Ubuntu Installing Package" src="https://i0.wp.com/farm8.staticflickr.com/7376/13030974504_9a91c15ee9_d.jpg?resize=500%2C204" width="500" height="204" data-recalc-dims="1" /> 

再次執行要安裝的指令後便沒有問題了

所以在安裝新的**Package**的時候建議先執行  
&#8220;<span style="color: #008000;"><strong>sudo apt-get update</strong></span>&#8221;

Hope you find it useful