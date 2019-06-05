---
id: 3922
title: 'RaspberryPi Auto connect Wifi &#8211; RaspberryPi 如何自動連接Wifi 網絡'
date: 2017-03-18T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3922
permalink: '/2017/03/raspberrypi-auto-connect-wifi-raspberrypi-%e5%a6%82%e4%bd%95%e8%87%aa%e5%8b%95%e9%80%a3%e6%8e%a5wifi-%e7%b6%b2%e7%b5%a1/'
categories:
  - RaspberryPi
---
之前和大家介紹過如何在**RaspberryPi setup wifi**

設定好之後再次開機&#8230;可惜又不能自動連接wifi

做了一會research之後發現解決方法十分簡單  
我們只需要開啟 **Interface的 settings**  
我們可以使用以下指令

<pre>sudo nano /etc/network/interfaces
</pre>

在檔案較上方的位置加上

<pre>auto wlan0

和較底的位置 加上
allow-hotplug wlan0
iface wlan0 inet dhcp</pre>

去話比Pi知道用**DHCP**  
<img class="alignnone size-large wp-image-3924" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=625%2C276" alt="config network interface to auto connect on wifi wlan0" width="625" height="276" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=1024%2C452 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=300%2C133 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=768%2C339 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=624%2C276 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?w=1333 1333w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
之後執行 以下指令 去 ensure 是用**dhcp**

<pre>sudo dhclient wlan0
</pre>

<img class="alignnone size-large wp-image-3923" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=625%2C151" alt="run sudo dhcpclient wlan0 to set wlan0 to use dhcp" width="625" height="151" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=1024%2C248 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=300%2C73 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=768%2C186 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=624%2C151 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?w=1071 1071w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> 

這便可以了  
Good Luck

Hope you find it useful