---
id: 3791
title: 'package android.support.v7.internal.widget.ActivityChooserModel does not exist android.support.v7 &#8211; Xamarin'
date: 2016-12-21T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3791
permalink: /2016/12/package-android-support-v7-internal-widget-activitychoosermodel-does-not-exist-android-support-v7-xamarin/
categories:
  - Xamarin
tags:
  - Xamarin
  - Xamarin Forms
---
最近重新安裝電腦後又再次開始學習**Xamarin Form**了

第一個練習當然是學習寫一個簡單的Map程式來看看  
誰不知..當我安裝**Xamarin.Forms.Maps** 之後Build的時候便出現了以下的錯誤信息..

&#8221; <span style="color: #ff0000;"><strong>Severity Code Description Project File Line Suppression State</strong></span>  
<span style="color: #ff0000;"><strong>Error error: package android.support.v7.internal.widget does not exist</strong></span>  
<span style="color: #ff0000;"><strong> private native void n_onInflate (android.support.v7.internal.widget.ViewStubCompat p0, android.view.View p1); XamarinDemo.Droid C:\Users\yauch\Documents\GitHub\XamarinDemo\XamarinDemo\XamarinDemo.Droid\obj\Debug\android\src\mono\android\support\v7\internal\widget\ViewStubCompat_OnInflateListenerImplementor.java 33</strong> </span>  
&#8221;

**解決方法**  
我們只要**Clean Solution** 之後再**Build**便可以了  
[<img class="alignnone size-large wp-image-3794" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?resize=625%2C352" alt="Visual Studio- Clean Solution" width="625" height="352" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?resize=1024%2C577 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?resize=300%2C169 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?resize=768%2C433 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?resize=624%2C352 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?w=1404 1404w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/ClearSolutions.png)  
Hope you find it useful