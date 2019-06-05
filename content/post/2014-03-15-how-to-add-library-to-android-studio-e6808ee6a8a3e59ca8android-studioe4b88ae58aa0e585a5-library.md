---
id: 3094
title: 'How to Add Library to Android Studio &#8211; 怎樣在Android Studio上加入 Library'
date: 2014-03-15T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3094
permalink: '/2014/03/how-to-add-library-to-android-studio-%e6%80%8e%e6%a8%a3%e5%9c%a8android-studio%e4%b8%8a%e5%8a%a0%e5%85%a5-library/'
categories:
  - Android
tags:
  - Android studio
---
對於使用**Android Studio** 找 **Android** / **Java** 的新手來說  
怎樣在**Android Studio**上加入 **Library** 可能是一個經常出現的問題..

我在學習過程中看到有很多不同的方法..  
很多時候他都都敎我們把**Library** 放到 &#8220;Libs&#8221;的資料夾上..  
之後又要在**Gradle** 檔案內加入一些**reference** / **設定**等的東西..  
才可以使用

經過多天的研究後發現原來在  
**Android Studio** 上加入**Library**是得容易的事來的&#8230;  
只是把你想使用的**Java Library**  
放在**Android Studio Project** 上的 &#8220;**libs**&#8220;資料夾內..  
我的例子是&#8221;**Google Play Services**&#8221; Library &#8220;**google-play-services.jar**&#8221;

在更新**Android Studio** 到**5.1.0**後發現

[xml]  
compile fileTree(dir: &#8216;libs&#8217;, include: [&#8216;*.jar&#8217;])  
[/xml]

在&#8221;**build.gradle**&#8220;上 好像已經有設定..只要在&#8221;**libs**&#8220;上的&#8221;**.jar**&#8220;檔案都會被**Compile**  
<img class="alignnone" alt="Android Studio build.gradle" src="https://i1.wp.com/farm3.staticflickr.com/2820/13201777683_4aa28ab493_z.jpg?resize=625%2C561" width="625" height="561" data-recalc-dims="1" /> 

這應該可以解決 **Add Library**時要自行在&#8221;**build.gradle**&#8220;上加入一些設定的問題

如果是使用較舊的**Android Studio**或者需要自行在這個**.jar**上按  
Mouse右按鈕..選擇&#8221;**Add as Library**&#8221;  
<img class="alignnone" alt="Android Studio - Add as Library" src="https://i0.wp.com/farm4.staticflickr.com/3672/13201635395_4ece77a238_z.jpg?resize=625%2C566" width="625" height="566" data-recalc-dims="1" />  
**Android Studio** 便會在&#8221;**build.gradle**&#8220;上加入相關的設定..  
你便可以開始使用這個**Library**了

Hope you find it useful