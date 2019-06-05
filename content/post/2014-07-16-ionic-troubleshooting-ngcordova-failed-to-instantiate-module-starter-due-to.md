---
id: 3299
title: 'Ionic troubleshooting &#8211; ngcordova Failed to instantiate module starter due to'
date: 2014-07-16T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3299
permalink: /2014/07/ionic-troubleshooting-ngcordova-failed-to-instantiate-module-starter-due-to/
categories:
  - Ionic Framework
tags:
  - Android
  - ionic troubleshooting
  - ngcordova
---
今天嘗試跟著 **ngCordova** 的例子和文章  
<a title="NgCordova Documentation" href="http://ngcordova.com/docs/" target="_blank">http://ngcordova.com/docs/</a>  
嘗試使用**ngCordova plugins**/**Library**/ **wrapper** 來開發一些 **Android** 程式  
我在他的&#8221;**Custom Build**&#8221; 頁面上下載了我需要的**ngCordova Plugins  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3867/14862771256_759b6ae8af_z.jpg?resize=625%2C305" alt="ngCordova Custom Build" width="625" height="305" data-recalc-dims="1" />**  
之後自行在我的**ionic** 資料夾上建立了 &#8220;<span style="color: #008000;"><strong>lib/ngCordova/dist</strong></span>&#8221; 資料夾來儲存這個js 檔

之後在&#8221;<span style="color: #008000;"><strong>js/app.js</strong></span>&#8220;上登記了 &#8216;**ngCordova**&#8216;

**E.G.**

<pre>angular.module('starter', ['ngCordova', 'ionic', 'starter.controllers'])
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3887/14885414152_d5d43350ef_z.jpg?resize=625%2C175" alt="Add ngCordova Module to Ionic's app.js" width="625" height="175" data-recalc-dims="1" />  
誰不知當我在**preview**的的**Ionic Application**時出現空白頁面

在檢查**Google Chrome Console**上看到以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Uncaught Error: [$injector:modulerr] Failed to instantiate module starter due to:</strong></span>  
<span style="color: #ff0000;"><strong> Error: [$injector:modulerr] Failed to instantiate module ngCordova due to:</strong></span>  
<span style="color: #ff0000;"><strong> Error: [$injector:nomod] Module &#8216;ngCordova&#8217; is not available! You either misspelled the mod&#8230;&#8230;1)</strong></span>&#8221;

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3905/14885414092_133e257f2b_z.jpg?resize=625%2C281" alt="[$injector:modulerr] Failed to instantiate module starter due to" width="625" height="281" data-recalc-dims="1" /> 

做了一會research之後發現..  
原來我們需要使用 **bower**來安裝 **ngCordova** 才能使用的

**解決方法**

我們可以在這個**Ionic** 的**Application** 資料來上  
用**NodeJs**的**Command prompt**輪入以下 指令來安裝

<pre>bower install -SF ngCordova
</pre>

<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3855/14905616453_d68e45aa83_z.jpg?resize=432%2C640" alt="Bower Install ngCordova" width="432" height="640" data-recalc-dims="1" /> 

如果嘗試安裝 **Bower**時出現問題..,可以嘗試參考以下網誌..看看能不能解決

## <a href="http://blog.sharechiwai.com/2014/07/bower-is-not-recognized-as-an-internal-or-external-command/" rel="bookmark">‘bower’ is not recognized as an internal or external command</a> {.entry-title}

安裝完成後再次執行這個**Ionic Application**

<pre>ionic serve
</pre>

**Ionic Application** 成功在**Browser**上顯示正常資訊了  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5590/14885738055_9d0384c492_z.jpg?resize=625%2C326" alt="Ionic Application with ngCordova Plugins" width="625" height="326" data-recalc-dims="1" /> 

Hope it solve your issue