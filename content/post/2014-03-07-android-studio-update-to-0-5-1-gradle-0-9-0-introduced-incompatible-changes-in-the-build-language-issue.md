---
id: 3074
title: 'Android Studio Update to 0.5.1 &#8211; Gradle 0.9.0 introduced incompatible changes in the build language issue'
date: 2014-03-07T00:00:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3074
permalink: /2014/03/android-studio-update-to-0-5-1-gradle-0-9-0-introduced-incompatible-changes-in-the-build-language-issue/
categories:
  - Android
tags:
  - Android studio
---
今天發現**Android Studio** 有更新&#8230; 可以更新到 **0.5.1** (**Build number: 134.1061098**)  
誰不知..更新完之後出現了問題&#8230;  
&#8220;<span style="color: #ff0000;"><strong>Failed to refresh Gradle project</strong></span>  
<span style="color: #ff0000;"><strong> The project is using an unsupported version of the Android Gradle plug-in (0.8.3).</strong></span>

<span style="color: #ff0000;"><strong>Version 0.9.0 introduced incompatible changes in the build language.</strong></span>&#8221;  
<img class="alignnone" alt="Failed to refresh Gradle project - Version 0.9.0 introduced incompatible changes in the build language." src="https://i0.wp.com/farm4.staticflickr.com/3376/13016981535_7fdb16f8d5_d.jpg?resize=500%2C340" width="500" height="340" data-recalc-dims="1" /> 

之後叫我去下面的網頁看看怎樣解決這個升級的問題&#8230;  
<a title="Android Studio Update paper" href="http://tools.android.com/tech-docs/new-build-system/migrating_to_09" target="_blank">http://tools.android.com/tech-docs/new-build-system/migrating_to_09</a>

看了一會..都不明白我的**Project** 要更新那些東西..  
因為我的程式內**Gradle** 的設定和他那個網頁上的..大至相同&#8230;

當我按**Make Project** 的時候..他又出現以下的錯誤信息&#8230;  
<img class="alignnone" alt="Failed to refresh Gradle project  - Version 0.9.0 introduced incompatible changes in the build language." src="https://i2.wp.com/farm3.staticflickr.com/2644/13017151393_01758f41a5_d.jpg?resize=500%2C103" width="500" height="103" data-recalc-dims="1" /> 

最後終於找到了**解決方法**了&#8230;

如果你看了**Android Studi**o 給你的升級提示..  
又覺得不識的話.. 可以嘗試以下的解決方法

**解決方法**十分簡單&#8230;  
在**Android Studio**的 **Project** 上 的**最面層** **Root Layer**  
有一個名叫&#8221;**build.gradle**&#8220;的**gradle設定檔**  
開啟這個檔案之後你便會看到一些和這個**Project**上的設定  
E.G. 有**Build Script** 等等  
在**Dependencies**上 的**Classpath** 找出一個以  
&#8220;<span style="color: #008000;"><strong>com.android.tools.build.gradle:</strong></span>&#8221; 開頭的 句子 把他修改成 **0.9.+**便可以了

我的是這樣的

[xml]  
dependencies {  
classpath &#8216;com.android.tools.build:gradle:0.8.+&#8217;  
}  
[/xml]

<img class="alignnone" alt=" classpath 'com.android.tools.build:gradle:0.8.+'" src="https://i0.wp.com/farm8.staticflickr.com/7407/13017377524_9186301d24_d.jpg?resize=500%2C340" width="500" height="340" data-recalc-dims="1" /> 

把他改成

[xml]  
dependencies {  
classpath &#8216;com.android.tools.build:gradle:0.9.+&#8217;  
}  
[/xml]

<img class="alignnone" alt="classpath 'com.android.tools.build:gradle:0.9.+'" src="https://i2.wp.com/farm8.staticflickr.com/7301/13017151143_50fba3ac8d_d.jpg?resize=486%2C211" width="486" height="211" data-recalc-dims="1" /> 

儲存之後按一下上方的&#8221;**Try Again**&#8220;..令**Android Studio**再次**Sync**這個**Gradle**

之後應該可以解決這個問題的

Hope you find is useful