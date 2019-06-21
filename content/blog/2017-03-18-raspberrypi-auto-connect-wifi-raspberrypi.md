---
id: 3922
title: 'RaspberryPi Auto connect Wifi - RaspberryPi 如何自動連接Wifi 網絡'
date: 2017-03-18T00:00:33+08:00
author: ShareChiWai
layout: post
categories:
  - RaspberryPi
---

之前和大家介紹過如何在**RaspberryPi setup wifi**

設定好之後再次開機
可惜又不能自動連接 wifi

做了一會 research 之後發現解決方法十分簡單
我們只需要開啟 **Interface 的 settings**
我們可以使用以下指令

```
sudo nano /etc/network/interfaces
```

在檔案較上方的位置加上

```
auto wlan0

和較底的位置 加上
allow-hotplug wlan0
iface wlan0 inet dhcp
```

去話比 Pi 知道用**DHCP**
<img class="alignnone size-large wp-image-3924" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/Piautoconnect.png?resize=625%2C276" alt="config network interface to auto connect on wifi wlan0" width="625" height="276"/>
之後執行 以下指令 去 ensure 是用**dhcp**

```
sudo dhclient wlan0
```

<img class="alignnone size-large wp-image-3923" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/wlan0dhcp.png?resize=625%2C151" alt="run sudo dhcpclient wlan0 to set wlan0 to use dhcp" width="625" height="151"/>

這便可以了
Good Luck

Hope you find it useful
