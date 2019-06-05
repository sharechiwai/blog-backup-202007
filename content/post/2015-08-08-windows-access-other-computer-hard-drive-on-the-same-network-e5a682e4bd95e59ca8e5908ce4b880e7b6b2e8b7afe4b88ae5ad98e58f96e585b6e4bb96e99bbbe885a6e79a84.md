---
id: 3458
title: 'Windows Access Other Computer Hard Drive on the same network &#8211; 如何在同一網路上存取其他電腦的儲存內容'
date: 2015-08-08T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3458
permalink: '/2015/08/windows-access-other-computer-hard-drive-on-the-same-network-%e5%a6%82%e4%bd%95%e5%9c%a8%e5%90%8c%e4%b8%80%e7%b6%b2%e8%b7%af%e4%b8%8a%e5%ad%98%e5%8f%96%e5%85%b6%e4%bb%96%e9%9b%bb%e8%85%a6%e7%9a%84/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Hacking
  - Security
---
在**Windows** 上如果我們有其他電腦的管理員權限.  
當其他電腦也是在同一網路上時  
我們可以使用 **電腦網路名稱**, **硬碟名稱** 加&#8221;**$**&#8221; 來存取他們的硬碟資料  
E.G.  
存取電腦 &#8220;**sharechiwai-pc**&#8220;的 c碟 可以輸入

<pre>\\sharechiwai-pc\c$
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3858/14218090359_7a170d2aa7_z.jpg?resize=625%2C304" alt="Access c$" width="625" height="304" data-recalc-dims="1" /> 

之後便會叫你輸入登入資料..  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5490/14404741735_cb28bab344_z.jpg?resize=574%2C385" alt="Windows Security ask for security info" width="574" height="385" data-recalc-dims="1" /> 

如何你知道那部電腦的登入資料或是他們是用和你一樣的User Group的話  
應該是可以開啟的

Hope you find it useful