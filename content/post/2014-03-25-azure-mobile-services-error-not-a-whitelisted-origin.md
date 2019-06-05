---
id: 3107
title: 'Azure Mobile Services &#8211; Error: Not a whitelisted origin'
date: 2014-03-25T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3107
permalink: /2014/03/azure-mobile-services-error-not-a-whitelisted-origin/
categories:
  - Microsoft Azure
tags:
  - Windows Azure Mobile Services
---
今天在測試**Windows Azure Mobile Services** 的時出現以下的錯誤  
<span style="color: #ff0000;"><strong>{&#8220;code&#8221;:401,&#8221;error&#8221;:&#8221;Error: Not a whitelisted origin: http://wagbc2014.azurewebsites.net&#8221;}</strong></span>  
<img class="alignnone" alt="{" src="https://i1.wp.com/farm8.staticflickr.com/7020/13304482255_808b233db8_o.jpg?resize=625%2C83" width="625" height="83" data-recalc-dims="1" />  
起初還以為 是Twitter/ Google / FaceBook OAuth/ Microsoft Account Oauth的問題  
誰不知其實是**Windows Azure Mobile Services**的安全性設定問題..

**解決方法**十分簡單..  
我們只需要登入**Windows Azure Portal**  
<a title="Manage Microsoft Azure" href="https://manage.windowsazure.com" target="_blank">https://manage.windowsazure.com</a>  
之後選擇&#8221;**Mobile Services**&#8221;  
-> 按一下你所使用的 **Mobile Services** 名稱  
之後按&#8221;**Configure**/**配置**&#8221;  
在 &#8220;**Configure**/**配置**&#8220;版面上 的中間部  
有一個 &#8220;**cross-origin resource sharing (cors)**&#8220;的部分  
在這裡你可以設定**Windows Azure Mobile Service**容許那一個網址可以Make Request 到這個**Mobile Services**上  
只要在**TextBox** 內加入你會使用**Windows Azure Mobile Services**的網址  
E.G.  
<img class="alignnone" alt="Windows Azure cross-origin resource sharing (cors)" src="https://i2.wp.com/farm8.staticflickr.com/7012/13304632083_9c5ac838f1_c.jpg?resize=625%2C663" width="625" height="663" data-recalc-dims="1" />  
按&#8221;**Save**/**儲存**&#8221; 便可以了

Hope you find it useful