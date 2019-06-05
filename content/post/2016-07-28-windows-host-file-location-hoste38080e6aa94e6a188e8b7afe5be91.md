---
id: 3706
title: 'Windows Host File Location &#8211; Host　檔案路徑'
date: 2016-07-28T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3706
permalink: '/2016/07/windows-host-file-location-host%e3%80%80%e6%aa%94%e6%a1%88%e8%b7%af%e5%be%91/'
categories:
  - 工作經驗/體驗/工作心得分享
tags:
  - Best Practices
  - Development Environment
  - Vagrant
---
和朋友嘗試建立一個比較完整的**Development Environment**  
我們使用了**Vagrant** 來做我們的**Server**, 所有程式碼都會在裡面執行  
這可以排除程式只在**local version** 可以成功執行的問題  
為了**環境一致**

我們還建立了一個**development**的**host name**  
朋友叫我在電腦上的 **host file**加入以下的句子

<pre>192.168.56.101    sharechiwai.dev
</pre>

之後在**browser**上輸入**sharechiwai.dev** 便會自動map 到 這個IP 上  
**192.168.56.101**

**192.168.56.101** **是vagrant的 default IP**

如果想在同一**IP address**上　**map　**到不同的　**host/domain**　我們需要把所有的　**hostname**/**domain　**加在同一行  
以空間分開

**e.g.**

<pre>192.168.56.101    sharechiwai.dev　chi.dev
</pre>

<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8776/28610796735_fbfeea2dfb_z.jpg?resize=625%2C520" alt="Host File Content" width="625" height="520" data-recalc-dims="1" />  
那麼在**Windows** 上的 **Host file** 儲存在那裡呢?  
他是存在以下路徑的

<pre>C:\Windows\System32\drivers\etc
</pre>

<img class="alignnone" src="https://i2.wp.com/farm9.static.flickr.com/8824/28503940412_4cbd402bdc_z.jpg?resize=625%2C262" alt="Windows Host file path" width="625" height="262" data-recalc-dims="1" />  
Hope you find it useful