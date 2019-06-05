---
id: 3927
title: 'Shutdown / power off RaspberryPi &#8211; RaspberryPi 如何安全關機?'
date: 2017-03-20T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3927
permalink: '/2017/03/shutdown-power-off-raspberrypi-raspberrypi-%e5%a6%82%e4%bd%95%e5%ae%89%e5%85%a8%e9%97%9c%e6%a9%9f/'
categories:
  - RaspberryPi
tags:
  - RaspberryPi
  - RaspberryPi Troubleshooting
---
最近常常使用**RaspberryPi**  
由于是用**SSH** 去連接&#8230;  
通常都是**unplug power cable**來關機  
所以不知道怎樣正確地關機

做了一會research後發現 解決方法十分簡單

**解決方法**

我們可以使用 **linux** 的關機 <span style="color: #008000;"><strong>shutdown</strong></span> command 來關機  
<span style="color: #008000;"><strong>-h</strong> </span>是馬上關機  
e.g.

<pre>sudo shutdown -h
</pre>

[<img class="alignnone size-large wp-image-3928" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?resize=625%2C129" alt="Command to Power off RaspberryPi Immediately " width="625" height="129" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?resize=1024%2C211 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?resize=300%2C62 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?resize=768%2C158 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?resize=624%2C128 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?w=1302 1302w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powerOffPi.png)

之前我的做法是使用其他電腦去**Ping** 這個**RaspberryPi**  
當他 **timeout**時便應該是已經關機了  
[<img class="alignnone size-large wp-image-3929" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?resize=625%2C253" alt="Try to ping RaspberryPi" width="625" height="253" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?resize=1024%2C415 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?resize=300%2C122 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?resize=768%2C311 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?resize=624%2C253 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png?w=1172 1172w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/pingPi.png)  
其實當**RaspberryPi** 的燈關沒有再閃  
或 如果你是使用**Powerbank** 時  
**Raspberry Pi**的燈關掉了  
便證明你的**RaspberryPi安全關機**

[<img class="alignnone size-full wp-image-3931" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg?resize=625%2C352" alt="powered off raspberry pi, without flash light" width="625" height="352" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg?w=800 800w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg?resize=300%2C169 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg?resize=768%2C432 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg?resize=624%2C351 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/powered-off-pi.jpg)

Hope you find it useful