---
id: 3288
title: 'Ionic platform add android Error: spawn ENOENT'
date: 2014-07-12T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3288
permalink: /2014/07/ionic-platform-add-android-error-spawn-enoent/
categories:
  - Ionic Framework
tags:
  - Android
  - Hybrid App
  - ionic troubleshooting
---
今天嘗試跟著**Ionic Framework** 的時  
<a title="Ionic Framework Tutorial" href="http://ccoenraets.github.io/ionic-tutorial/index.html" target="_blank">http://ccoenraets.github.io/ionic-tutorial/index.html</a>  
當我嘗試使用**ionic platform** 指令加入**Android Platform**

<pre>ionic platform add android
</pre>

出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;">events.js:72</span>  
 <span style="color: #ff0000;">throw erl // Unhandled &#8216;error&#8217; event</span>  
** <span style="color: #ff0000;">Error: spawn ENOENT</span>**  
&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3919/14866891925_ca787179c4_z.jpg?resize=625%2C207" alt="Ionic Framework - Error: spawn ENOENT" width="625" height="207" data-recalc-dims="1" /> 

這個錯誤是在我更新了**Ionic Framework CLI** 之後才出現的

### <a href="http://blog.sharechiwai.com/2014/07/how-to-update-ionic-cli-%e5%a6%82%e4%bd%95%e6%9b%b4%e6%96%b0ionic-framework-cli/" rel="bookmark">How to Update Ionic CLI- 如何更新Ionic Framework CLI</a> {.entry-title}

做了一會research之後  
找到了暫時的解決方法

**解決方法**:  
我們只需要暫時安裝另一個版本的 **Ionic Framework CLI**便可以解決這個問題

E.g. 我安裝了 **ionic 1.1.9 beta1**  
在**NodeJs**的**command prompt** 上輸入以下指令便可以了

<pre>npm install -g ionic@1.1.9-beta1
</pre>

<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5567/14680271749_4b8c937aac_z.jpg?resize=600%2C640" alt="Install Ionic Framework 1.1.9 beta 1" width="600" height="640" data-recalc-dims="1" /> 

安裝完成後..再次執行

<pre>ionic platform add android
</pre>

**ionic platform** 指令加入**Android Platform**  
出現&#8221;<span style="color: #ff0000;"><strong>Platform android already added</strong></span>&#8221; 應該是正常的..因為我之前嘗試使用**cordova** 指令來加入**Android Platform** 來解決&#8221;<span style="color: #ff0000;"><strong>Error: spawn ENOENT</strong></span>&#8221; 的問題&#8230;

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3882/14680271759_3b03571170_z.jpg?resize=625%2C206" alt="Ionic Framework:  Platform android already added" width="625" height="206" data-recalc-dims="1" /> 

之後再用 **ionic** 指令來**Build** 這個程式

<pre>ionic build android
</pre>

最後使用**Ionic** 指令嘗試在 **Android Emulator**上 執行這個**Ionic Hybrid App**

<pre>ionic emulate android
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3891/14680375397_e047131acd_z.jpg?resize=625%2C575" alt="Ionic Tutorial run on Android Emulator" width="625" height="575" data-recalc-dims="1" /> 

Hope it solve your issue.