---
id: 3335
title: 'VT not Supported &#8211; This computer does not support Intel Virtualization Tech nology (VT0x). HAXM cannot be installed.'
date: 2015-01-02T00:00:27+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3335
permalink: /2015/01/vt-not-supported-this-computer-does-not-support-intel-virtualization-tech-nology-vt0x-haxm-cannot-be-installed/
categories:
  - Android
tags:
  - HAXM
  - Intel
  - Tizen
---
今天當我嘗試安裝 **Intel Hardware Accelerated Execution Manager** 時  
他出現了以下的錯誤信息

&#8220;**<span style="color: #ff0000;">VT not Supported &#8211; This computer does not support Intel Virtualization Tech</span>**  
** <span style="color: #ff0000;">nology (VT0x). HAXM cannot be installed. Please refer to the Intel HAXM documentation for more information.</span>**&#8221;

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7461/15496125723_fcb0dcb40f_z.jpg?resize=625%2C490" alt="VT not Supported - This computer does not support Intel Virtualization Tech nology (VT0x). HAXM cannot be installed. Please refer to the Intel HAXM documentation for more information." width="625" height="490" data-recalc-dims="1" /> 

原因是因為 **Intel Virtualization Technology 是**不可以和 **Hyper-V** 共同安裝..  
所以便要暫時解決安裝 **Hyper-V** 才可以安裝 **Intel HAXM**了

**解決方法**

我們以在電腦上的 &#8220;**Control Panel**&#8220;-> &#8220;**Programs and Features**&#8221;  
之後選擇 &#8220;**Turn Windows features on or off**&#8221;  
之後 untick &#8220;**Hyper-V**&#8221; 的check box  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7571/16115944555_6727c11896_z.jpg?resize=625%2C456" alt="Enable/Disable Hyper-V" width="625" height="456" data-recalc-dims="1" />  
按&#8221;**OK**/**確定**&#8221;  
之後他便會叫你重新啟動電腦

重新啟動電腦後便可以安裝 &#8220;**Intel Hardware Accelerated Execution Manager**&#8221; 了

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7501/15493493674_65f45709cc_z.jpg?resize=625%2C490" alt="Install Intel Hardware Accelerated Execution Manager HAXM" width="625" height="490" data-recalc-dims="1" /> 

Hope you find it useful