---
id: 3569
title: RaspberryPi How to get current OS version
date: 2016-02-02T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3569
permalink: /2016/02/raspberrypi-how-to-get-current-os-version/
categories:
  - RaspberryPi
tags:
  - Linux
  - Linux Command
  - RaspberryPi
---
最近開始玩**RaspberryPi** 由於想試不同的 **RaspberryPi OS** /**Build**  
所以便安裝了多不同的**Image**去不同的 **SD卡**  
不久問題便開始出現了..  
就是不知道現在是用緊那一個那 **RaspberryPi OS** 的  
[因為我都是用**SSH** 去**Config**, 沒有電視去看他的**GUI**]

做了一會Research 之後終於找到解決方法了

**解決方法**  
我們可以在**Command Prompt 上輸入以下指令**  
[相信這指令可以在 任何Linux 上執行的]

<pre>cat /etc/os-release
</pre>

之後他便出現了 這個 **RaspberryPi的 資訊**了  
E.G.  
這是 **Raspbian Version 8 Jessie** 等等  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1456/24123385393_41d7418b43_z.jpg?resize=625%2C370" alt="RaspberryPi Info" width="625" height="370" data-recalc-dims="1" /> 

Hope you find it useful