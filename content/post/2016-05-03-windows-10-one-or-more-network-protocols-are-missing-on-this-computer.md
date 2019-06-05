---
id: 3649
title: Windows 10 One or more network protocols are missing on this computer
date: 2016-05-03T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3649
permalink: /2016/05/windows-10-one-or-more-network-protocols-are-missing-on-this-computer/
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - troubleshooting
  - Windows 10
---
今日朋友做完**Windows 10** 更新 之後出現了不知上網的問題  
使用了 <span style="color: #3366ff;"><strong>Windows Network Diagnostics</strong></span>  
來做 Troubleshooting 之後他的結果是  
&#8220;<span style="color: #ff0000;"><strong>One or more network protocols are missing on this computer</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7102/26764213326_a0227ff685_z.jpg?resize=625%2C499" alt="One or more network protocols are missing on this computer" width="625" height="499" data-recalc-dims="1" />  
做了很多測試也不能解決.  
E.G. 在 **ipconfig**中..這部電腦的 IP address 是**169.254.137.122**  
相信是不能上網的原因

做了一會Research之後終於找到解決方法了

**解決方法**:  
我在可以使用**Command Prompt**去 **Renew IP Address** 應該便可以解決這問題的  
可以嘗試執行以下指令

<pre>ipconfig /flushdns

ipconfig /registerdns

ipconfig /release

ipconfig /renew
</pre>

Hope you find it useful