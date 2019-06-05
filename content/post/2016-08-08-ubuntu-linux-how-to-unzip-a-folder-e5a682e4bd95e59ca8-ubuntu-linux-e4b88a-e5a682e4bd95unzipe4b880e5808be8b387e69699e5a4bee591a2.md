---
id: 3728
title: 'Ubuntu / Linux How to UnZip a folder &#8211; 如何在 Ubuntu / Linux 上 如何UnZip一個資料夾呢?'
date: 2016-08-08T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3728
permalink: '/2016/08/ubuntu-linux-how-to-unzip-a-folder-%e5%a6%82%e4%bd%95%e5%9c%a8-ubuntu-linux-%e4%b8%8a-%e5%a6%82%e4%bd%95unzip%e4%b8%80%e5%80%8b%e8%b3%87%e6%96%99%e5%a4%be%e5%91%a2/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - Ubuntu
---
之前的筆記寫下

### <a href="http://blog.sharechiwai.com/2016/08/ubuntu-linux-how-to-zip-a-folder-%e5%a6%82%e4%bd%95%e5%9c%a8-ubuntu-linux-%e4%b8%8a-%e5%a6%82%e4%bd%95zip%e4%b8%80%e5%80%8b%e8%b3%87%e6%96%99%e5%a4%be%e5%91%a2/" rel="bookmark">Ubuntu / Linux How to Zip a folder – 如何在 Ubuntu / Linux 上 如何Zip一個資料夾呢?<br /> </a> {.entry-title}

今日想和大家分享 如何在 **Ubuntu** / **Linux** 上 **如何UnZip一個資料夾**  
**解決方法**十分簡單

如果想把**Zipped** 檔案直接在這個地方**Unzip** 我𠍒只需要執行

<span style="color: #0000ff;"><strong>unzip</strong> </span><span style="color: #008000;">ZippedFileName.Zip</span>

<pre>unzip WebFolder.zip
</pre>

如果想 **Unzip** **檔案/資料夾到另一個 Directory/資料夾.**. 可以使用 &#8220;**-d**&#8221; 去指定一個資料夾  
E.G.  
<span style="color: #0000ff;"><strong>unzip <span style="color: #008000;">ZippedFile</span> -d [<span style="color: #008000;">Destination folder</span>]</strong></span>

<pre>unzip websiteBack.zip -d /public_html
</pre>

Hope you find it useful