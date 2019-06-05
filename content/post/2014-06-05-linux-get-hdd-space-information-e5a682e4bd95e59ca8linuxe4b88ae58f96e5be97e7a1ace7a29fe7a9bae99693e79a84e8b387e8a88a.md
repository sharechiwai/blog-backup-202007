---
id: 3213
title: 'Linux Get HDD Space information &#8211; 如何在Linux上取得硬碟空間的資訊'
date: 2014-06-05T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3213
permalink: '/2014/06/linux-get-hdd-space-information-%e5%a6%82%e4%bd%95%e5%9c%a8linux%e4%b8%8a%e5%8f%96%e5%be%97%e7%a1%ac%e7%a2%9f%e7%a9%ba%e9%96%93%e7%9a%84%e8%b3%87%e8%a8%8a/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Ubuntu
---
在**Azure**上建立了一個**Ubuntu Server**的**Virtual Machine**  
很想知道這個**Virtual Machine**佔用了多小的空間  
[因為當我在建立這個**Virtual Machine** 時沒有選項給我選擇想要的空間大少]

**解決方法**十分簡單..  
我們可以使用&#8221;**df**&#8220;這個 **Command**/指令來取得 硬碟空間的資訊

**DF** 的意思是 **Disk FileSystem**

  * **-T 變數是顯示 File System Type**
  * **-h 變數把數據以GB來顯示**
  * **-m 變數把數據以MB來顯示**

我多數會使用 以下的指令

<pre><strong>df -T -h</strong>
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3838/14437102732_98a6424e4b_z.jpg?resize=625%2C229" alt="Microsoft Azure Check default Linux Virtual Machine Hard Drive Space" width="625" height="229" data-recalc-dims="1" /> 

Hope you find it useful