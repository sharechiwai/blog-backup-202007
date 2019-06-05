---
id: 3349
title: '&#8216;zipalign&#8217; is not recognized as an internal or external command, operable program or batch file'
date: 2015-01-10T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3349
permalink: /2015/01/zipalign-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file/
categories:
  - Android
tags:
  - ionic troubleshooting
---
在準備發佈我的**Ionic Android** 程式到 **Google Play Store** 前 需要使用 **zipalign** 來把這個 **APK** 優化。。。  
可惜當我使用 **zipalign** 指令時。。  
出現了以下的錯誤信息  
&#8220;&#8216;<span style="color: #ff0000;"><strong>zipalign&#8217; is not recognized as an internal or external command, operable program or batch file</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7513/15970140189_4595cb30af_z.jpg?resize=625%2C78" alt="'zipalign' is not recognized as an internal or external command, operable program or batch file" width="625" height="78" data-recalc-dims="1" /> 

很多時候遇到 &#8220;<span style="color: #ff0000;"><strong>&#8216;xxx&#8217; is not recognized as an internal or external command, operable program or batch file</strong></span>&#8221; 都是因為 &#8220;**Environment Variable**&#8221; 沒有設定好

我在想..像**adb** 這些 **Android SDK**的**tools**都可以用到..  
所以應該不是 &#8220;**Environment Variable**&#8221; 的 Path的問題

做了一會research之後發現

原來**zipalign.exe**.不是儲存在我們**android SDK tool** 這個資料夾內。。

<pre><span style="color: #008000;"><strong>"C:\Users\[Username]\AppData\Local\Android\sdk\tools"
</strong></span></pre>

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7523/16156205225_5fb6f273fe_z.jpg?resize=625%2C321" alt="Android SDK Tools Folder" width="625" height="321" data-recalc-dims="1" />  
而是在。。

<pre><span style="color: #008000;"><strong>"C:\Users\[Username]\AppData\Local\Android\sdk\build-tools\[Build version]"
</strong></span></pre>

**<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8623/16155453142_e494ca817c_z.jpg?resize=625%2C316" alt="Android SDK Build Tools" width="625" height="316" data-recalc-dims="1" />  
解決方法**。。  
把 **zipalign** 從 &#8220;**build-tools**&#8220;的資料夾內  
複製到 &#8220;**tools**&#8221; 的資料夾內

之後便可以成功使用 zipalign 指令了  
<img class="alignnone" src="https://i2.wp.com/farm9.static.flickr.com/8670/15968892200_0b3875d924_z.jpg?resize=625%2C264" alt="ZipAlign tools work" width="625" height="264" data-recalc-dims="1" /> 

Hope you find it useful

<!-- Tech-Blog-bottom-Content-336x280 -->

  
<ins class="adsbygoogle"
     style="display:inline-block;width:336px;height:280px"
     data-ad-client="ca-pub-4266560994470212"
     data-ad-slot="3788424641"></ins>