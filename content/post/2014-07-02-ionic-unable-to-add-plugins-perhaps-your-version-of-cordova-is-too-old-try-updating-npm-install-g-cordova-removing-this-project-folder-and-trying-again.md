---
id: 3262
title: 'Ionic &#8211; Unable to add plugins. Perhaps your version of Cordova is too old. Try updating (npm install -g cordova), removing this project folder, and trying again.'
date: 2014-07-02T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3262
permalink: /2014/07/ionic-unable-to-add-plugins-perhaps-your-version-of-cordova-is-too-old-try-updating-npm-install-g-cordova-removing-this-project-folder-and-trying-again/
categories:
  - Ionic Framework
tags:
  - Cordova
  - ionic troubleshooting
---
一開始學習**Ionic Framework**便碰丁  
當我嘗試跟著教學 建立我第一個**Ionic Project**的時候..  
出現了以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Unable to add plugins. Perhaps your version of Cordova is too old. Try updating</strong></span>  
<span style="color: #ff0000;"><strong> (npm install -g cordova), removing this project folder, and trying again.</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3911/14817424474_bc9e9f1f02_z.jpg?resize=625%2C445" alt="Unable to add plugins. Perhaps your version of Cordova is too old. Try updating (npm install -g cordova), removing this project folder, and trying again" width="625" height="445" data-recalc-dims="1" /> 

我嘗試使用他的建議去更新電腦上的 **cordova**  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5556/14633158488_94c962acf5_z.jpg?resize=625%2C200" alt="Update Cordova - npm install -g cordova" width="625" height="200" data-recalc-dims="1" /> 

之後再次建立新的**Ionic Project**  
可惜結果都是一樣..  
之後我便你細地看看這些錯誤信息..

**詳細資料**:

> **<span style="color: #ff0000;">Error: Command failed: fatal: could not create work tree dir &#8216;C:\Users\Chi\AppDa</span>**  
> ** <span style="color: #ff0000;">ta\Local\Temp\plugman\git\1407081827937&#8242;.: No such file or directory</span>**
> 
> **<span style="color: #ff0000;">at ChildProcess.exithandler (child_process.js:648:15)</span>**  
> ** <span style="color: #ff0000;">at ChildProcess.emit (events.js:98:17)</span>**  
> ** <span style="color: #ff0000;">at maybeClose (child_process.js:756:16)</span>**  
> ** <span style="color: #ff0000;">at Socket. (child_process.js:969:11)</span>**  
> ** <span style="color: #ff0000;">at Socket.emit (events.js:95:17)</span>**  
> ** <span style="color: #ff0000;">at Pipe.close (net.js:465:12)</span>**  
> ** <span style="color: #ff0000;">Unable to add plugins. Perhaps your version of Cordova is too old. Try updating</span>**  
> ** <span style="color: #ff0000;">(npm install -g cordova), removing this project folder, and trying again.</span>**

其中有一句是說 &#8220;<span style="color: #ff0000;"><strong>AppData\Local\Temp\plugman\git\</strong></span>&#8221; **No such File or directory** / **沒有這個資料夾**  
所以我便開啟電腦上這個資料夾查看&#8230;  
發現&#8221;**plugman**&#8220;這個資料夾真是不存在..  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3853/14819792005_7a71cf1a69_z.jpg?resize=625%2C319" alt="AppData/Local/Temp" width="625" height="319" data-recalc-dims="1" /> 

所以我便嘗試新增需要的暫存資料夾 &#8220;**plugman**&#8221;  
在&#8221;**plugman**&#8220;入再新增&#8221;**git**&#8220;資料夾  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2928/14819792045_2e2a0b9a12_z.jpg?resize=625%2C315" alt="plugman folder on AppData\Local\Temp" width="625" height="315" data-recalc-dims="1" /> 

之後再次執行 **ionic**來建立新的**Application**

結果..  
成功了

<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3925/14817424584_cf71a57b61_z.jpg?resize=529%2C640" alt="Successfully create Ionic Framework Application" width="529" height="640" data-recalc-dims="1" /> 

Hope you find it useful