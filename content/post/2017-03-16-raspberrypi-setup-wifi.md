---
id: 3916
title: RaspberryPi setup wifi
date: 2017-03-16T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3916
permalink: /2017/03/raspberrypi-setup-wifi/
categories:
  - RaspberryPi
tags:
  - RaspberryPi
  - RaspberryPi setup
---
終於解決了 **SSH** 的問題  
現在 用 LAN 線是可以連接的  
但是**Raspberry Pi3** 其中一個吸引之處是有**built-in Wifi**  
如何設定**wifi** 呢  
**解決方法**  
我們只需要在 <span style="color: #008000;"><strong>wpa_supplicant.conf</strong></span> 加上Wifi setting便可以了

假設你已經知道 **Wifi** 的 **SSID** 和有**password** 了  
你便可以在**Raspberry pi**的 **console/terminal**上轉入

<pre>sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
</pre>

去開啟**wifi** 設定.. 之後加入 **Wifi** 的設定  
<img class="alignnone size-full wp-image-3920" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/nano-wpa_supplicant.png?resize=625%2C235" alt="nano open wpa_supplicant.conf" width="625" height="235" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/nano-wpa_supplicant.png?w=671 671w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/nano-wpa_supplicant.png?resize=300%2C113 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/nano-wpa_supplicant.png?resize=624%2C234 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
**SSID** = <span style="color: #0000ff;"><strong>Wifi 名</strong></span>  
**PSK** =  <span style="color: #0000ff;"><strong>Wifi Password</strong></span>  
<img class="alignnone size-large wp-image-3919" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?resize=625%2C270" alt="Enter Wifi detail onto wpa_supplicant.conf" width="625" height="270" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?resize=1024%2C443 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?resize=300%2C130 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?resize=768%2C332 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?resize=624%2C270 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pi-wifi-detail.png?w=1283 1283w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
E.G.

<pre>network={
    ssid="wifi name"
    psk="wifi password"
    id_string="optional"
}
</pre>

如果是使用<span style="color: #008080;"><strong>nano editor</strong></span>的話可以按 &#8220;**CTRL**&#8221; + &#8220;**X**&#8221; 之後按 &#8220;**Y**&#8221; 和 &#8220;**Enter**&#8220;便可以儲存了  
<img class="alignnone size-full wp-image-3918" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/sudo-wpa_cli-reconfigure.png?resize=625%2C112" alt="run sudo wpa_cli reconfigure to refresh wifi / wpa settings" width="625" height="112" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/sudo-wpa_cli-reconfigure.png?w=889 889w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/sudo-wpa_cli-reconfigure.png?resize=300%2C54 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/sudo-wpa_cli-reconfigure.png?resize=768%2C138 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/sudo-wpa_cli-reconfigure.png?resize=624%2C112 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
儲存後再執行以下指令去 **reconfig** 這個設定

<pre>sudo wpa_cli reconfigure
</pre>

之後可以執行 **ifconfig wlan0**來看看能不能連接網絡

<pre>ifconfig wlan0
</pre>

<img class="alignnone size-large wp-image-3917" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?resize=625%2C165" alt="run ifconfig wlan0 to check wlan0 status" width="625" height="165" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?resize=1024%2C270 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?resize=300%2C79 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?resize=768%2C203 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?resize=624%2C165 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?w=1330 1330w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/ifconfig-wlan0.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
如果可以看到 **inet address** 有**IP** 便可以了

hope you find it useful