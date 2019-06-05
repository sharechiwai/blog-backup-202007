---
id: 1866
title: 'VirtualBox Use Router&#8217;s DHCP &#8211; VirtualBox 用Router派 IP Address 安裝與設定 Debian Server'
date: 2011-07-11T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1866
permalink: '/2011/07/virtualbox-use-routers-dhcp-virtualbox-%e7%94%a8router%e6%b4%be-ip-address-%e5%ae%89%e8%a3%9d%e8%88%87%e8%a8%ad%e5%ae%9a-debian-server/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Virtual Box
  - Virtual Machine
---
為了可以嘗試使用的電腦系統..我決定了安裝一個**Virtual Machine** 來建立一個測試環境

**測試環境小小比較:**  
選擇Virtual Machine  
由於Virtual PC感覺上比較佔用很多的資源  
VMWare 免費版本又沒有得使用Snapshot這個功能  
最後決定使用VirtualBox 了  
[身邊得多朋友都是使用 VirtualBox 的]

終於在**VirtualBox**上 安裝了**Apache Web Server**  
之後發現問題出現了..  
由於**Default Setting的VirtualBox Client**是使用 **NAT** 的關係  
所以他的IP Address 是  
**10.0.2.25** [應該會是任何一個以10.0 開始的IP address]  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0450940d1f464cf7a2406793f17f4e5f/renditions/fullsize.jpg?resize=617%2C292" alt="" width="617" height="292" data-recalc-dims="1" /> 

**DHCP Server**  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d44bb4d280264dd1b3aabe8b4fd9961b/renditions/fullsize.jpg?resize=625%2C310" alt="" width="625" height="310" data-recalc-dims="1" />  
由於不是和我的電腦差不多..  
[在不同的Network的關係]

所以便連接不到這個Server

現在便要想想如何在**VirtualBox**上 使用自己**Network上的 Router 以DHCP 派發IP 給這部 Virtual Machine**了

**解決方法十分簡單**  
在**VirtualBox** 程式上選擇你想**用Router的DHCP派IP 的Virtual Machine**..  
按滑鼠右鍵..  
之後選擇&#8221;**Settings&#8230;/設定&#8230;**&#8221;

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cf134210381149c0b285a031df2c4ad6/renditions/fullsize.jpg?resize=625%2C220" alt="" width="625" height="220" data-recalc-dims="1" /> 

選擇&#8221;**Network/網絡選項**&#8220;..  
在預設的情況下&#8221;**Adapter 1**&#8221; 會自己被啟用 和 選擇了&#8221;**NAT**&#8221; 的  
我們只需要把&#8221;**Attached to**:&#8221; 從&#8221;**NAT**&#8221; 轉成&#8221;**Bridged Adapter**&#8220;便可以了  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/85a02d20046049d6a0b17bb1d5d9a764/renditions/fullsize.jpg?resize=593%2C286" alt="" width="593" height="286" data-recalc-dims="1" /> 

Hope you find it useful