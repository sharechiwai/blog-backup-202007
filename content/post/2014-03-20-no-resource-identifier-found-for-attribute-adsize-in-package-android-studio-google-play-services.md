---
id: 3098
title: 'no resource identifier found for attribute &#8216; adsize &#8216; in package &#8211; Android Studio &#8211; Google Play Services'
date: 2014-03-20T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3098
permalink: /2014/03/no-resource-identifier-found-for-attribute-adsize-in-package-android-studio-google-play-services/
categories:
  - Android
tags:
  - Android studio
  - Android Studio 0.5.1
  - Google Play Services
---
最近幾天都在嘗試學習如何在**Android Studio**上使用 **Google Play Services AdMob**  
之前的**Android App** 是用**Admob SD**K的

之前出現了  
<a title="UNEXECTED TOP-LEVEL EXCEPTION – com.android.dex.decExeption: Mulitiple dex file define" href="http://blog.sharechiwai.com/2014/03/unexected-top-level-exception-com-android-dex-decexeption-mulitiple-dex-file-define/" target="_blank">UNEXECTED TOP-LEVEL EXCEPTION &#8211; com.android.dex.decExeption: Mulitiple dex file defin</a>e的問題  
<img alt="UNEXECTED TOP-LEVEL EXCEPTION - com.android.dex.decExeption: Mulitiple dex file define" src="https://i1.wp.com/farm3.staticflickr.com/2782/13202980233_473680445c_z.jpg?resize=625%2C200" width="625" height="200" data-recalc-dims="1" />  
所以我便刪除了

[xml]  
compile &#8216;com.google.android.gms:play-services:4.2.42&#8217;  
compile files(&#8216;libs/google-play-services.jar&#8217;)  
[/xml]

使用**Android Studio 0.5.1** **build.gradle**上的

[xml]  
compile fileTree(dir: &#8216;libs&#8217;, include: [&#8216;*.jar&#8217;])  
[/xml]

嘗試做了很久Research..試了很多方法..可惜都解決不到  
&#8220;<span style="color: #ff0000;"><strong>no resource identifier found for attribute &#8216; adUnitId &#8216; in package android studio</strong></span>&#8221;

最後嘗試以直角去解決這個問題&#8230;終於能幸運地解決 =)

**解決方法**  
應該是更新了**Android Studio 0.5.1 Gradle**的處理放法不同的關係..  
所以有小小混亂

解決這個問題  
我們需要**Comment out** /或**刪去**在**build.gradle**上的

[xml]  
compile fileTree(dir: &#8216;libs&#8217;, include: [&#8216;*.jar&#8217;])  
[/xml]

之後再加上**Google Play Services**的 參考  
我的方法是  
在**Android Project**上按Right Click -> 選擇&#8221;**Open Module Settings**&#8221;  
<img class="alignnone" alt="Android Studio - Open Module Settings" src="https://i2.wp.com/farm8.staticflickr.com/7422/13251763324_a2edda72f8_z.jpg?resize=625%2C637" width="625" height="637" data-recalc-dims="1" />  
之後便會出現&#8221;**Project Structure**&#8221; Windows &#8220;**Project Settings**&#8221; -> &#8220;**Module**&#8221;  
在右手邊有一些選項..  
選擇 &#8220;**Dependencies**&#8221;  
之後按&#8221;**+**&#8221; -> 選擇&#8221;**Library Dependency**&#8221;  
<img class="alignnone" alt="Project Structure - Module -> Library Dependency" src="https://i0.wp.com/farm8.staticflickr.com/7051/13251763274_8b4f70c586_c.jpg?resize=625%2C116" width="625" height="116" data-recalc-dims="1" />  
&#8220;**Choose Library Dependency**&#8221; windows 便會彈出來..  
我們可以在這裡選擇 &#8220;**Google Play Services**&#8221;  
<img class="alignnone" alt="Android Studio - Choose Library Dependency" src="https://i1.wp.com/farm4.staticflickr.com/3799/13251413715_a138476cd9_z.jpg?resize=625%2C282" width="625" height="282" data-recalc-dims="1" />  
之後按&#8221;**OK**&#8221;  
他便會在**build.gradle**加入一些和**Google Play Service**相關的設定/參考  
<img class="alignnone" alt="Android Studio - build.gradle" src="https://i1.wp.com/farm8.staticflickr.com/7147/13251413725_dd0c905433_o.png?resize=524%2C156" width="524" height="156" data-recalc-dims="1" />  
完成後再次**Compile**這個**Project**  
之後便可以解決這個問題了  
&#8220;<span style="color: #ff0000;"><strong>no resource identifier found for attribute &#8216; adUnitId &#8216; in package</strong></span>&#8221; 的錯誤便會消失了

Hope you find it useful