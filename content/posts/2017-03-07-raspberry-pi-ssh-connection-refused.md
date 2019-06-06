---
id: 3901
title: Raspberry pi ssh connection refused
date: 2017-03-07T07:07:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3901
permalink: /2017/03/raspberry-pi-ssh-connection-refused/
categories:
  - RaspberryPi
tags:
  - IoT
  - RaspberryPi
  - RaspberryPi Troubleshooting
---
見朋友開始玩 **RaspberryPi**的關係  
我也再次想試試看自己可以用**RaspberryPi** 來做些什麼東西

當我**Download**和 Load 了最新的[RASPBIAN JESSIE LITE](https://www.raspberrypi.org/downloads/raspbian/) 後便出現了一些問題

還記得之前設定和安裝**RaspberryPi**的過程也十分順利的

當我嘗試**SSH** 到這個**RaspberryPi** 時 出現了  
&#8220;<span style="color: #ff0000;"><strong>Raspberry pi ssh connection refused</strong></span>&#8221; 的錯誤信息  
做了一會research 之後&#8230;  
發現2016年 11月出的**Raspbian** 預設是停用了 **SSH Server**的

如果想要啟用**SSH**  
便要把**RaspberryPi** 連接 Monitor 和Keyboard 去他的console上設定了

**解決方法**  
**登入 raspberrypi**後輸入

<pre>sudo raspi-config
</pre>

之後選擇 &#8220;<span style="color: #008000;"><strong>Interface options</strong></span>&#8221; -> &#8220;<span style="color: #008000;"><strong>SSH</strong></span>&#8221;  
選擇 &#8220;<span style="color: #008000;"><strong>OK</strong></span>&#8221;  
之後便可以了

Hope you find it useful