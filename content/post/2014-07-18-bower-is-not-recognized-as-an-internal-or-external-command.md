---
id: 3302
title: '&#8216;bower&#8217; is not recognized as an internal or external command'
date: 2014-07-18T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3302
permalink: /2014/07/bower-is-not-recognized-as-an-internal-or-external-command/
categories:
  - Ionic Framework
tags:
  - bower
  - ionic troubleshooting
  - ngcordova
  - NodeJs
---
今天嘗試使用 **bower**來安 &#8220;**ngCordova**&#8221; 時出現以下的錯誤信息  
在之前的網誌裡有和大家分享介紹..如果要在Ionic Framework中使用 &#8220;**ngCordova**&#8221;  
是要用 **bower**來安裝的

## <a href="http://blog.sharechiwai.com/2014/07/ionic-troubleshooting-ngcordova-failed-to-instantiate-module-starter-due-to/" rel="bookmark">Ionic troubleshooting – ngcordova Failed to instantiate module starter due to</a> {.entry-title}

<pre>bower install -SF ngCordova
</pre>

&#8220;&#8216;<span style="color: #ff0000;"><strong>bower&#8217; is not recognized as an internal or external command,</strong></span>  
<span style="color: #ff0000;"><strong> operable program or batch file.</strong></span>&#8221;

原因是因為在這部電腦上沒有安裝 **Bower**

**解決方法**十分簡單  
我們可以使用**NodeJs**的**Command Prompt** 之後輸入**NodeJs**指令來安裝  
**&#8211; g**的意思 **Install Globally** 是給所有使用者用

**解決方法**

<pre>npm install -g bower
</pre>

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5592/14862763776_5c88bdc456_z.jpg?resize=617%2C640" alt="Install Bower via NodeJs npm" width="617" height="640" data-recalc-dims="1" />  
Hope you find it useful