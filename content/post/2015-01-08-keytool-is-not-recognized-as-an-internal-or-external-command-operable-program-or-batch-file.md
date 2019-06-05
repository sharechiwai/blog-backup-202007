---
id: 3347
title: '&#8216;keytool&#8217; is not recognized as an internal or external command, operable program or batch file'
date: 2015-01-08T13:02:30+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3347
permalink: /2015/01/keytool-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file/
categories:
  - Ionic Framework
tags:
  - Java
---
嘗試跟著**Ionic Framework**的 **Official Document  
http://ionicframework.com/docs/guide/publishing.html  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7523/15965753318_0105d4f244_z.jpg?resize=625%2C53" alt="Keytool instructions from Ionic Publishing page" width="625" height="53" data-recalc-dims="1" />  
** 

使用 **keytool**來 **sign**我的 **Ionic Android APK**時出現以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>&#8216;keytool&#8217; is not recognized as an internal or external command, operable program or batch file</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7567/15530854624_9d77a5a62f_z.jpg?resize=625%2C70" alt="'keytool' is not recognized as an internal or external command, operable program or batch file" width="625" height="70" data-recalc-dims="1" /> 

應該是**Environment Variable**上的 **Path** 有些問題而造成的

**解決方法**

在電腦上找出安裝在電腦上的 **Java Bin 資料夾**  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7581/15965753408_c1e38540a7_z.jpg?resize=625%2C303" alt="Java Bin Folder Path" width="625" height="303" data-recalc-dims="1" /> 

<pre>E.G.
C:\[Program Files 或 Program Files (x86)]\Java\[jdk version]\bin
我的bin folder是在這裡的
C:\Program Files\Java\jdk1.8.0_25\bin
</pre>

之後加進 電腦的 **Environment Variable**的 &#8220;**path**&#8221; 屬性上  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7566/15967433017_e73e59df74_z.jpg?resize=459%2C537" alt="Environment Variable - Path property" width="459" height="537" data-recalc-dims="1" /> 

之後重新啟動 **command prompt**便可以了  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7547/15965753298_4a79c971d0_z.jpg?resize=625%2C371" alt="Keytool command works" width="625" height="371" data-recalc-dims="1" /> 

Hope you find it useful

<!-- Tech-Blog-bottom-Content-336x280 -->

  
<ins class="adsbygoogle"
     style="display:inline-block;width:336px;height:280px"
     data-ad-client="ca-pub-4266560994470212"
     data-ad-slot="3788424641"></ins>