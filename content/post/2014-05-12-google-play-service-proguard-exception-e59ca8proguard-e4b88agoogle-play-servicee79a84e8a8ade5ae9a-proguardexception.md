---
id: 3179
title: 'Google Play Service Proguard Exception &#8211; 在ProGuard 上Google Play Service的設定 #ProguardException'
date: 2014-05-12T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3179
permalink: '/2014/05/google-play-service-proguard-exception-%e5%9c%a8proguard-%e4%b8%8agoogle-play-service%e7%9a%84%e8%a8%ad%e5%ae%9a-proguardexception/'
categories:
  - Android
tags:
  - Proguard
  - ProguardException
---
相信很多寫Android App的朋友都有**Proguard**來**obfuscation** 他們的程式碼

為了方便自己不用到**Google** 去搜尋 **Google Play Service**的**Proguard Exception**設定  
所以便在這裡分享這個常用的 設定

<pre>-keep class * extends java.util.ListResourceBundle {
    protected Object[][] getContents();
}

-keep public class com.google.android.gms.common.internal.safeparcel.SafeParcelable {
    public static final *** NULL;
}

-keepnames @com.google.android.gms.common.annotation.KeepName class *
-keepclassmembernames class * {
    @com.google.android.gms.common.annotation.KeepName *;
}

-keepnames class * implements android.os.Parcelable {
    public static final ** CREATOR;
}
</pre>

<img class="alignnone" src="https://i1.wp.com/farm3.staticflickr.com/2927/14402142733_08c3c24b18_z.jpg?resize=625%2C409&#038;ssl=1" alt="ProGuard Google Play Services Exception" width="625" height="409" data-recalc-dims="1" /> 

詳情可以參考以下的網址  
<a title="Set up Google Play Services" href="http://developer.android.com/google/play-services/setup.html" target="_blank">http://developer.android.com/google/play-services/setup.html</a>

在這建立一個Tag 來記下所有**Proguard**的 Exception Rules  
**#ProguardException**

Hope you find it useful