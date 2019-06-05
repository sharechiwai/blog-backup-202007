---
id: 3552
title: How to get ISO checksum on Windows
date: 2016-01-18T00:00:36+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3552
permalink: /2016/01/how-to-get-iso-checksum-on-windows/
categories:
  - Vagrant 筆記
tags:
  - Microsoft
  - Packer.io
  - Vagrant
---
最近開始學習怎樣建立 **Vagrant Box**  
希望係不久既將來可以自己建立一些**vagrant box** 在公司 或自己用  
我們需要使用 <a href="https://www.packer.io/" target="_blank"><strong>Packer</strong> [<strong>packer.io</strong>]</a>這個工具來 建立 **vagrant box**  
其中建立**VagrantBox的Template**上需要轉入 **ISO** 和他的**CheckSum**的資料  
主要是用來認證 要安裝的 ISO 檔案沒有損壞先安裝吧

上網做了很多research都是教如何在**Linux**找出檔案的**Checksum**..  
很小有說**Windows**可以怎樣做  
最後終於找到**解決方法**了.

大家可以到以下的**Microsoft**的網頁  
<a href="https://www.microsoft.com/en-gb/download/details.aspx?id=11533" target="_blank">https://www.microsoft.com/en-gb/download/details.aspx?id=11533</a>  
下載 &#8220;**<a href="https://www.microsoft.com/en-gb/download/details.aspx?id=11533" target="_blank">Microsoft File Checksum Integrity Verifier</a>**&#8221;  
解壓縮後便可以使用**Command prompt** 來執行  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1594/24060109554_7bb386c957_z.jpg?resize=480%2C206" alt="Microsoft File Checksum Integrity Verifier" width="480" height="206" data-recalc-dims="1" />  
入面有**Readme** 檔介紹怎樣使用的

<pre>fciv [File Path \ FileName] [hash type e.g. md5 / sha1]

F:\CheckSum&gt;fciv f:\ubuntu-15.10-server-amd64.iso -md5
//
// File Checksum Integrity Verifier version 2.05.
//
fb4eef05edcabfc5cccd4cb44f3f9b48 f:\ubuntu-15.10-server-amd64.iso
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1456/24594730811_936c4afe3d_z.jpg?resize=625%2C315" alt="Windows File Checksum " width="625" height="315" data-recalc-dims="1" />  
Hope you find it useful