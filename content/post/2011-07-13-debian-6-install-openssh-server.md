---
id: 1870
title: Debian 6 Install OpenSSH Server
date: 2011-07-13T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1870
permalink: /2011/07/debian-6-install-openssh-server/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Openssh
---
安裝好**Debian/Linux** 之後..  
第一個安裝的軟件是 **OpenSSH Server**  
他的好處時我們可以通過**SSH** 的**Client**  
如: **Putty** 用Command的 方式登入 這個**Linux Server**  
之後便像在主機當中..不用使用**Remote Desktop** 去登入主機中了  
另一個好處是..我們可以使用**Copy and Paste**..  
如果你在主機中.. 是不可以**copy and paste**不在主機上的文字的

**設定/安裝OpenSSH**  
我們只是輸入以下指令便可以了  
**<span style="color: #008000;">apt-get install openssh-server</span>**

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8d7c0597f31847fa96bc7fd8de7a62d7/renditions/fullsize.jpg?resize=625%2C340" alt="" width="625" height="340" data-recalc-dims="1" /> 

之後可以檢查Server 的**IP Address** 是什麼..之後便可以使用**Putty** 來連接這電腦了  
可以輸入Command  
<span style="color: #008000;"><strong>ifconfig</strong></span>  
詳情可以參考以下URL  
 <a title="Linux Check IP address – 在Linux上檢查自己的IP Address" href="http://blog.sharechiwai.com/2011/07/linux-check-ip-address-%e5%9c%a8linux%e4%b8%8a%e6%aa%a2%e6%9f%a5%e8%87%aa%e5%b7%b1%e7%9a%84ip-address/" target="_blank">Linux Check IP address – 在Linux上檢查自己的IP Address</a>

Hope you find it useful