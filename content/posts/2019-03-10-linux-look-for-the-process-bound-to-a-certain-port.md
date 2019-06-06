---
id: 4131
title: Linux look for the process bound to a certain port
date: 2019-03-10T11:02:10+08:00
author: ShareChiWai
layout: post
guid: https://blog.sharechiwai.com/?p=4131
permalink: /2019/03/linux-look-for-the-process-bound-to-a-certain-port/
image: /wp-content/uploads/2019/03/BindAddressAlreadyInUse-624x99.png
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux Command
---
今日嘗試執行 **Docker-Compose** 去啟動Nginx Container 時出現以下的錯誤信息  
<figure class="wp-block-image">

<img src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?fit=625%2C99&ssl=1" alt="Cannot start service nginx: driverfailed programming external connectivity on endpoint nginx 
 erland proxy: listen tcp 0.0.0.0:80: bind: address already in use" class="wp-image-4133" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?w=1671 1671w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?resize=300%2C47 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?resize=768%2C121 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?resize=1024%2C162 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?resize=624%2C99 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/BindAddressAlreadyInUse.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" /> <figcaption> _Cannot start service nginx: driverfailed programming external connectivity on endpoint nginx_  
 _erland proxy: listen tcp 0.0.0.0:80: bind: address already in use_ </figcaption></figure> 

原因是因為 port 80 已經在使用中..  
怎樣知道那些process 正在使用 port 80呢?  
我們可以使用以下command

<pre class="wp-block-preformatted">sudo lsof -i -P -n | grep ":80 (LISTEN)"</pre><figure class="wp-block-image">

<img src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?fit=625%2C81&ssl=1" alt="linux command check which process use specific port" class="wp-image-4135" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?w=1261 1261w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?resize=300%2C39 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?resize=768%2C100 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?resize=1024%2C133 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/checkSpecificPortInUse.png?resize=624%2C81 624w" sizes="(max-width: 625px) 100vw, 625px" /> <figcaption>Linux command check which process use specific port</figcaption></figure> 

知道那些process 正在使用port :80之後 我們便可以 kill 了他們<figure class="wp-block-image">

<img src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?fit=625%2C146&ssl=1" alt="Kill Linux Process" class="wp-image-4136" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?w=1313 1313w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?resize=300%2C70 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?resize=768%2C180 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?resize=1024%2C240 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?resize=624%2C146 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/killProcess.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" /> <figcaption>kill process</figcaption></figure> 

Hope you find it useful