---
id: 3096
title: 'UNEXECTED TOP-LEVEL EXCEPTION &#8211; com.android.dex.decExeption: Mulitiple dex file define'
date: 2014-03-18T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3096
permalink: /2014/03/unexected-top-level-exception-com-android-dex-decexeption-mulitiple-dex-file-define/
categories:
  - Android
tags:
  - Android studio
  - Android Studio 0.5.1
---
在更新了**Android Studio 0.5.1** 後很多時候跟隨教學的東西都用不著..  
今天我的學習過程中又出現了一些問題了  
在嘗試使用**Google Play Services** 的時候出現了以下的錯誤..  
<img class="alignnone" alt="UNEXECTED TOP-LEVEL EXCEPTION - com.android.dex.decExeption: Mulitiple dex file define" src="https://i1.wp.com/farm3.staticflickr.com/2782/13202980233_473680445c_z.jpg?resize=625%2C200" width="625" height="200" data-recalc-dims="1" />  
情況應該是這樣的..  
在**Android Studio 0.5.1**開始在 **build.gradle**上多了一句

[xml]  
compile fileTree(dir: &#8216;libs&#8217;, include: [&#8216;*.jar&#8217;])  
[/xml]

當我學習使用**Google Play Services**時我是使用**0.4.6** 版本的..  
所以便使用了之前 &#8220;<a title="How to Add Library to Android Studio – 怎樣在Android Studio上加入 Library" href="http://blog.sharechiwai.com/2014/03/how-to-add-library-to-android-studio-%e6%80%8e%e6%a8%a3%e5%9c%a8android-studio%e4%b8%8a%e5%8a%a0%e5%85%a5-library/" target="_blank">How to Add Library to Android Studio – 怎樣在Android Studio上加入 Library</a>&#8221;  
的&#8221;**Add as Library**&#8220;的方法 加入了 &#8220;**Google Play Services**&#8221;  
這個功能亦都在 **build.gradle**上加入了一些 **Reference**/**設定**

**E.g.**

[xml]  
compile &#8216;com.google.android.gms:play-services:4.2.42&#8217;  
compile files(&#8216;libs/google-play-services.jar&#8217;)  
[/xml]

就是因為這樣..在**Android Studio**上好像把 **google-play-services.jar**參考/Compile了兩次..  
第一次是

[xml]  
compile fileTree(dir: &#8216;libs&#8217;, include: [&#8216;*.jar&#8217;])  
[/xml]

另一次是

[xml]  
compile files(&#8216;libs/google-play-services.jar&#8217;)  
[/xml]

<img class="alignnone" alt="build.gradle has both references on dependencies" src="https://i1.wp.com/farm4.staticflickr.com/3769/13202980343_182fb8a3f8_o.png?resize=625%2C503" width="625" height="503" data-recalc-dims="1" />  
所以便出現了這個錯誤  
&#8220;<span style="color: #ff0000;"><strong>UNEXECTED TOP-LEVEL EXCEPTION &#8211; com.android.dex.decExeption: Mulitiple dex file define</strong></span>&#8221;

**解決方法十分簡單**  
我們只是刪除其中一個參考便可以了..  
我選擇刪除

[xml]  
compile &#8216;com.google.android.gms:play-services:4.2.42&#8217;  
compile files(&#8216;libs/google-play-services.jar&#8217;)  
[/xml]

之後再次**Compile**. .便沒有錯誤了

<img class="alignnone" alt="build.gradle without the google play services reference" src="https://i2.wp.com/farm4.staticflickr.com/3721/13202980213_5bb8db8a55_z.jpg?resize=625%2C297" width="625" height="297" data-recalc-dims="1" /> 

Hope you find it useful