---
id: 3726
title: 'Ubuntu / Linux How to Zip a folder &#8211; 如何在 Ubuntu / Linux 上 如何Zip一個資料夾呢?'
date: 2016-08-06T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3726
permalink: '/2016/08/ubuntu-linux-how-to-zip-a-folder-%e5%a6%82%e4%bd%95%e5%9c%a8-ubuntu-linux-%e4%b8%8a-%e5%a6%82%e4%bd%95zip%e4%b8%80%e5%80%8b%e8%b3%87%e6%96%99%e5%a4%be%e5%91%a2/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - Ubuntu
---
最近要進行 **VPS Server Migration** 為了方便重新上載和被備份網頁  
最簡單的方法是**Zip** 了整個Website Folder 之後download 或transfer file

那麼如何在 **Ubuntu** / **Linux** 上 **如何Zip一個資料夾**呢?

**解決方法**十分簡單

首先我們要在**Ubuntu** 上安裝 **Zip**和 **UnZip**這兩個Package  
e.g.

<pre>sudo apt-get install zip unzip
</pre>

之後我們便可以使用 zip 這個**Command** 來Zip 想要的 資料夾或檔案了

**Zip <span style="color: #008000;">ZipLevel</span>**[<span style="color: #0000ff;">R1-R9</span>] **<span style="color: #008000;">DestinationFile SourceFile</span>**  
E.G.

<pre>zip -r9 websiteBack.zip public_html
</pre>

Hope you find it useful