---
id: 3903
title: 'RaspberryPi &#8211; host does not exist'
date: 2017-03-08T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3903
permalink: /2017/03/raspberrypi-host-does-not-exist/
categories:
  - RaspberryPi
tags:
  - Putty
  - RaspberryPi
  - RaspberryPi Troubleshooting
  - SSH
---
發現 **RaspberryPi 3** 不能用**Host name** 來連接  
原本想使用**Putty** 輸入**Raspberry Pi** 的**Host Name** &#8220;**raspberrypi**&#8221;  
來**SSH** 塊 Pi  
誰不知..他出現以下的錯誤信息..  
&#8220;<span style="color: #ff0000;"><strong>Unable to open connection to raspberrypi</strong></span>  
<span style="color: #ff0000;"><strong>Host does not exist</strong></span>&#8221;  
<img class="alignnone wp-image-3904 size-full" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/host-does-not-exist.png?resize=517%2C351" alt="RaspberryPi - host does not exist" width="517" height="351" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/host-does-not-exist.png?w=517 517w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/host-does-not-exist.png?resize=300%2C204 300w" sizes="(max-width: 517px) 100vw, 517px" data-recalc-dims="1" />  
但是使用**IP address**是可以連接的  
這應該是 **RaspberryPi**的**Setting**問題  
做了一會Research..找到了解決方法

**解決方法**  
我們可以安裝 **samba**  
e.g.

<pre>sudo apt-get -y install samba
</pre>

[<img class="alignnone size-large wp-image-3905" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?resize=625%2C203" alt="install Samba" width="625" height="203" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?resize=1024%2C333 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?resize=300%2C97 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?resize=768%2C250 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?resize=624%2C203 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?w=1308 1308w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/installSamba.png)  
安裝完之後便解決了  
[<img class="alignnone size-large wp-image-3906" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?resize=625%2C378" alt="Hostname working on Raspberrypi" width="625" height="378" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?resize=1024%2C619 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?resize=300%2C181 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?resize=768%2C464 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?resize=624%2C377 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?w=1347 1347w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/HostNameWork-now.png)

Hope you find it useful