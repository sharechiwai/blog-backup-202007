---
id: 3269
title: 'Ionic &#8211; An error occurred while listing Android targets &#8211; Add platform target for building an Ionic app'
date: 2014-07-06T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3269
permalink: /2014/07/ionic-an-error-occurred-while-listing-android-targets-add-platform-target-for-building-an-ionic-app/
categories:
  - Ionic Framework
tags:
  - Android
  - ionic troubleshooting
  - troubleshooting
---
繼續跟著**Ionic Framework**的教學來建立我的**Ionic Framework** Hello World Project時  
雖然是可以成功安裝  
<a title="Ionic Framework -> Get Started" href="http://ionicframework.com/getting-started/" target="_blank">http://ionicframework.com/getting-started/<br /> </a>  
但是在執行指令去**Add Android platform**時

<pre>ionic platform add android
</pre>

出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Error from platform command &#8211; Add platform target for building an Ionic app</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5571/14634698710_d568587e0b_z.jpg?resize=580%2C640" alt="Error from platform command - Add platform target for building an Ionic app" width="580" height="640" data-recalc-dims="1" /> 

做了一會research後終於找到解**決方法**了

原來又是要設定一些&#8221;**Environment Variables**/ **環境變數**&#8221; 的問題  
[暫時所出現的問題..大部分都是因為電腦上沒有預先設定好一些&#8221;**Environment Variables**/ **環境變數**&#8221; 所以出現的]

**解決方法**  
在之前的網誌介紹了大家怎麼去設定&#8221;**Environment Variables** / **環境變數**&#8221;  
E.G.  
按一下&#8221;**Advanced System Settings**/**進階系統設定**&#8221; -> &#8220;**Advanced** tab/**進階** 分頁&#8221; ->&#8221;**Environment Variables** / **環境變數**&#8221; 按一下

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3843/14818343754_8cbbbf8c32_z.jpg?resize=562%2C580" alt="Environment Variables Settings" width="562" height="580" data-recalc-dims="1" />  
在&#8221;**System variable** / **系統變數**&#8221; 上新增 &#8220;**ANDROID_HOME**&#8221;

之後在 **Variable Value** 上加上你電腦上的**Android SDK**的資料夾  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3926/14841238343_d947da7682_z.jpg?resize=459%2C537" alt="Set up System Variables on Windows for ANDROID_HOME" width="459" height="537" data-recalc-dims="1" /> 

由于我之前是使用**Android Studio**的關係  
所以我的**Android SDK** 是在**Android Studio**的資料夾 [可能和你的不一樣]  
我的是在以下的路徑  
&#8220;<span style="color: #008000;"><strong>C:\Program Files (x86)\Android\android-studio\sdk</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3896/14821058052_c10dd192d4_z.jpg?resize=625%2C360" alt="Android Studio Android SDK Folder Path" width="625" height="360" data-recalc-dims="1" /> 

完成後

之後選擇&#8221;**System variable** / **系統變數**&#8221; 上的 &#8220;**path**&#8221;  
在最後一段文字上輸

<pre>;%ANDROID_HOME%\tools;%ANDROID_HOME%\platform-tools;
</pre>

這會使用你之前定義的**ANDROID_HOME**變數再加上**tools** / **platform-tools** 來話給電腦聽你的**Android SDK Tools** 和 **platform tools** 在那裡

<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2910/14634851057_339073c7fb_z.jpg?resize=459%2C537" alt="Environment Variables -> Path for Android SDK Tools and Platform tools path" width="459" height="537" data-recalc-dims="1" /> 

完成後可以回到**Ionic** / **NodeJs** 的**console**上再次執行

<pre>ionic platform add android
</pre>

問題應該解決了 &#8211; 你應該會看到和以下相似的畫面

<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3863/14634773018_46f093bf84_z.jpg?resize=625%2C640" alt="ionic platform add android works" width="625" height="640" data-recalc-dims="1" /> 

Happy Coding