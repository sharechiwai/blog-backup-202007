---
id: 3556
title: 'Packer hide Virtual Machine GUI &#8211; Packer 如何在建立Virtual Machine時 把介面隱藏'
date: 2016-01-20T21:12:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3556
permalink: '/2016/01/packer-hide-virtual-machine-gui-packer-%e5%a6%82%e4%bd%95%e5%9c%a8%e5%bb%ba%e7%ab%8bvirtual-machine%e6%99%82-%e6%8a%8a%e4%bb%8b%e9%9d%a2%e9%9a%b1%e8%97%8f/'
categories:
  - Vagrant 筆記
tags:
  - devops
  - Packer
  - Vagrant
---
在使用Packer的時候 **Virtual Box** 自動彈出了他的**VirtualBox GUI**出來  
我們可以看到安裝的過程, 十分有趣  
但是亦都有些擾亂自己..  
因為無端端多了個**Application**在**screen**上出現

如果我們不在執行 **Packer**時  
彈出**Virtual Machine的介面**  
我們可以在 **Packer的 Template 檔案上把 Headless的設定為 True**

> **headless (boolean) &#8211; Packer defaults to building VirtualBox virtual machines by launching a GUI that shows the console of the machine being built. When this value is set to true, the machine will start without a console.**  
>  **E.G.**

<pre>"disk_size": "{{user `disk_size`}}",
    "headless": "true",
    "http_directory": "http",
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1469/24594730791_9d48d8b0a9_z.jpg?resize=452%2C97" alt="Packer Hide Virtual Machine UI during Build - Headless = true" width="452" height="97" data-recalc-dims="1" />  
Hope you find it useful