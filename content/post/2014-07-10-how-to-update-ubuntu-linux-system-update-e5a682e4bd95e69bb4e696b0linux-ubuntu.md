---
id: 3278
title: 'How to update Ubuntu &#8211; Linux System Update &#8211; 如何更新Linux [Ubuntu]'
date: 2014-07-10T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3278
permalink: '/2014/07/how-to-update-ubuntu-linux-system-update-%e5%a6%82%e4%bd%95%e6%9b%b4%e6%96%b0linux-ubuntu/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Microsoft Azure
  - Ubuntu
---
在登入在**Microsoft Azure** 的 **Linux Ubuntu VM**的時候  
通常在**SSH** 到 那個**Ubuntu** VM時出現一些訊息  
E.G. **Ram/ CPU**/ 和**硬碟的使用量**等等

有時亦都會看到有多小**Package**可以更新  
E.G.  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3844/14824909605_ff2d9816be_z.jpg?resize=625%2C347" alt="Number of Linux Package can be update" width="625" height="347" data-recalc-dims="1" /> 

那麼如何更新**Linux** [**Ubuntu**]系統呢?

**解決方法**  
我們可以先執行

<pre>apt-get update 
</pre>

以確保我們大最新的**Update**資訊  
之後我們可以執行

<pre>sudo apt-get dist-upgrade 
</pre>

的指令到更新我們的**Linux** 系統  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5552/14638362137_ff6503a983_z.jpg?resize=616%2C100" alt="sudo apt-get dist-upgrade - upgrade Linux system" width="616" height="100" data-recalc-dims="1" /> 

之後**Linux**會出現一些資訊  
說有那些新的**Package**會被更新  
那些會是新安裝的  
還有安裝所需的硬碟空間等等..  
會問你是否希望繼續安裝  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3911/14824909625_e45fb11d78_z.jpg?resize=579%2C640" alt="Are you sure you want to continue to update Ubuntu packages" width="579" height="640" data-recalc-dims="1" />  
輸入&#8221;**y**&#8220;後按&#8221;**Enter**&#8221; 便會自己安裝了

這了一會便更新完成  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3849/14638199440_f3237a1ae6_z.jpg?resize=579%2C640" alt="Ubuntu Linux Update completed" width="579" height="640" data-recalc-dims="1" /> 

可能我是一個**Windows**思考的人  
所以還是重新啟動電腦比較安心一點

**在Linux上重新啟動系統**.我們可以執行以下的指令

<pre>sudo reboot
</pre>

Hope you find it useful