---
id: 3498
title: 'Ionic Error: EXDEV, cross-device link not permitted'
date: 2015-08-20T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3498
permalink: /2015/08/ionic-error-exdev-cross-device-link-not-permitted/
categories:
  - Ionic Framework
tags:
  - Cordova
  - ionic troubleshooting
  - Mobile Development
  - ngcordova
---
今天當我嘗試在我的 **Ionic Framework** Project 安裝 **cordova plugin** 時出現了以下的錯誤信息..

<pre><code class="language-text" data-lang="text">&lt;a href="https://github.com/phonegap-build/PushPlugin.git" target="_blank">cordova plugin add https://github.com/phonegap-build/PushPlugin.git&lt;/a></code></pre>

&#8220;<span style="color: #ff0000;"><strong>Error: EXDEV, cross-device link not permitted</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5826/20057976643_f555e5bc0d_z.jpg?resize=377%2C179" alt="Ionic Error: EXDEV, cross-device link not permitted" width="377" height="179" data-recalc-dims="1" />  
做了一會research 之後發現..  
應該是 電腦上安裝了的 **Corodova** 版本有問題..  
所以只需要 安裝舊一些的版本便可以解決這個問題

**解決方法**  
在 **command prompt** 上執行以下指令去安裝 指定版本的 **cordova**

<pre>npm install -g cordova@5.0.0
</pre>

<img class="alignnone" src="https://i2.wp.com/farm1.static.flickr.com/727/20490906228_3150ee6819_z.jpg?resize=284%2C40" alt="npm install -g cordova@ version" width="284" height="40" data-recalc-dims="1" />  
安裝完了再次嘗試安裝 這個**cordova** plugin..  
e.g. **Ionic** / **Cordova** **Push Notification** plugin

<pre>cordova plugin add https://github.com/phonegap-build/PushPlugin.git
</pre>

<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5803/20056366294_474540a89a_z.jpg?resize=625%2C130" alt="Able to install Cordova plugin" width="625" height="130" data-recalc-dims="1" /> 

成功安裝

Hope you find it useful