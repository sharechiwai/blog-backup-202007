---
id: 3067
title: Proguard rule for Google Play Services / Admob
date: 2014-02-28T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3067
permalink: /2014/02/proguard-rule-for-google-play-services-admob/
categories:
  - Android
tags:
  - Admob
  - Google Play Services
  - Proguard
---
如果在**Android** 程式上有使用**Google Play Services** 或 **Admob API**的朋友&#8230;  
當你使用**Proguard**的時候&#8230;  
有可能會令到這兩個**API**的功能出現問題&#8230;

大家只要在你們的**Proguard Config** 檔案內加內以下的設定便可以了  
E.G.  
**proguard.cfg**  
或  
**proguard-android.txt**

**Google Play Services**

[java]-keep public class com.google.android.gms.ads.*\* {public \*;}[/java]

**Admob API**

[java]-keep public class com.google.ads.*\* { public \*;}[/java]

詳情可以參考以下網頁  
<a title="Mobile Ads SDK - KnowledgeBase" href="https://developers.google.com/mobile-ads-sdk/kb/" target="_blank">https://developers.google.com/mobile-ads-sdk/kb/</a>  
Hope you find it useful