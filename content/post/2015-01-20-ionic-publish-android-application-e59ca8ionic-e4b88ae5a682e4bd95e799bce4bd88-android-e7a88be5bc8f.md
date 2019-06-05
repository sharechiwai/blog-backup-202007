---
id: 3376
title: 'Ionic Publish Android application &#8211; 在Ionic 上如何發佈 Android 程式'
date: 2015-01-20T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3376
permalink: '/2015/01/ionic-publish-android-application-%e5%9c%a8ionic-%e4%b8%8a%e5%a6%82%e4%bd%95%e7%99%bc%e4%bd%88-android-%e7%a8%8b%e5%bc%8f/'
categories:
  - Ionic Framework
tags:
  - Android
  - apk
---
回到英國之後.. 開始專注使用**Ionic Framework**來開發程式

因為常常想到新的功能..所以便常常要再發佈更新到 **Google PlayStore**

為了方便自己.還是寫一個筆記方便自己將來發佈 **Android** 程式

我相信大家還是在你的 **Ionic Project Directory**  
你可以使用以下指令 去建立 一個&#8221;**Release Build**&#8221;

<pre>cordova build --release android
</pre>

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7423/16337923246_8f781a09f9_z.jpg?resize=625%2C216" alt="Ionic Release Build" width="625" height="216" data-recalc-dims="1" />  
之後我們便需要去到輸出 apk 檔的 資料夾 以方便之前的動作  
通常在**Ionic Project**上的 <span style="color: #0000ff;"><strong>platforms\android\ant-build</strong> </span>資料夾上  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7300/15741445894_140749f340_z.jpg?resize=625%2C311" alt="Ionic Build directory" width="625" height="311" data-recalc-dims="1" /> 

**e.g.**

<pre>cd platforms\android\ant-build
</pre>

之後我們便會看到 **ionic generate** 的 **unsigned release apk**檔案  
<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8614/16176267738_7b3d9c90eb_z.jpg?resize=617%2C121" alt="CordovaApp-release-unsigned.apk on Ionic Build Folder" width="617" height="121" data-recalc-dims="1" /> 

之後我們便可以 **Sign** 這個 **unsigned release**的 **apk**了  
**Ionic default**的 **unsigned release apk**名是這樣的 &#8220;**CordovaApp-release-unsigned.apk**&#8221;

我們可以用以下指令到**簽署unsigned apk**

<pre>jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore [Full filename and path.keystore / 你的keystore的 路徑和檔案名] CordovaApp-release-unsigned.apk [alias name / 別名] 
</pre>

**e.g.**

<pre>jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore D:\Ionic\SampleProject\keystores\SharechiwaiDemoReleaseKey.keystore CordovaApp-release-unsigned.apk ShareChiWaiDemoReleaseKey 
</pre>

之後他們叫你輸入之前在這個**keystore**上設定的 密碼  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8571/15743917863_edf501d9cd_z.jpg?resize=625%2C210" alt="use jarsinger to sign unsigned apk" width="625" height="210" data-recalc-dims="1" />  
* **keystore** 是在之前的網誌上有介紹給大家如何建立自己的sign key

詳情可以參考以下網誌

<a title="Useful command for Android Development 1 – 一些有用的在開發Android程式時幾有用的指令筆記" href="http://blog.sharechiwai.com/2015/01/useful-command-for-android-development-1-%e4%b8%80%e4%ba%9b%e6%9c%89%e7%94%a8%e7%9a%84%e5%9c%a8%e9%96%8b%e7%99%bcandroid%e7%a8%8b%e5%bc%8f%e6%99%82%e5%b9%be%e6%9c%89%e7%94%a8%e7%9a%84%e6%8c%87/" target="_blank">Useful command for Android Development 1 – 一些有用的在開發Android程式時幾有用的指令筆記</a>

<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8612/15741445914_aa817e2a88_z.jpg?resize=625%2C229" alt="Ionic Android Signed Apk" width="625" height="229" data-recalc-dims="1" />  
完成後便可以使用 &#8220;**zipalign**&#8221; 功具來 優化 Android 程式.. 主要用來壓縮apk內的 圖/資料檔等等..  
以便**減輕記憶體/RAM 的使用量**

<pre>zipalign -v 4 CordovaApp-release-unsigned.apk [Your APK name / 你想出現的檔案名].apk
</pre>

e.g.

<pre>zipalign -v 4 CordovaApp-release-unsigned.apk sharechiwai_demo.apk
</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7391/15741445924_c85b00cea4_z.jpg?resize=625%2C193" alt="zipalign - compress apk" width="625" height="193" data-recalc-dims="1" />  
可以準備 Upload 你的 APK 了  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7369/16176512630_a484fd2a49_z.jpg?resize=625%2C97" alt="Signed APK with zipalign" width="625" height="97" data-recalc-dims="1" /> 

Hope you find it useful