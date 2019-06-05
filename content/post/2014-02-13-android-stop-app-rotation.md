---
id: 3055
title: Android Stop App Rotation
date: 2014-02-13T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3055
permalink: /2014/02/android-stop-app-rotation/
categories:
  - Android
---
今天發現自己的的一個**App** 有一個好大的問題..  
就是每當手機**Rotate**/**迴轉**時  
E.G. 從橫向轉為直向 或直向轉為橫向時  
這個**Activity** 都會 **Reload**/ **Recreate** 的..  
所以使用者會失去這程式上現在的數據&#8230;o

找到了一個簡單的解決方法&#8230;  
暫時解決這個問題

我們可以在這個**Android App** 上的 **Manifest** 的**Activity** Tag中  
E.g. <span style="color: #0000ff;"><strong>AndroidManifest.xml</strong></span> 上  
加入  
**<span style="color: #ff0000;">android:screenOrientation=&#8221;<span style="color: #000000;">portrait</span>/<span style="color: #000000;">landscape</span>..<span style="color: #000000;">etc</span>&#8220;</span>**

E.g. 假設的**Activity** 會設定為**直向的**/**Portrait**..  
我會加入這個**Property**/屬性  
**<span style="color: #ff0000;">android:screenOrientation=&#8221;portrait&#8221;</span>**  
在**Manifest** 的**Activity** Tag中的設定便會是這樣子的  
<img class="alignnone" alt="Android screen Orientation configuration" src="https://i2.wp.com/farm8.staticflickr.com/7451/12853070354_7b8af20a6a_o.png?resize=452%2C102" width="452" height="102" data-recalc-dims="1" /> 

[xml]  
<activity  
android:name="com.sharechiwai.blog.post"  
android:screenOrientation="portrait"  
android:label="@string/title\_activity\_blog"></activity>  
[/xml]

另一個方法&#8221;**savedInstanceState**&#8220;.. 要慢慢學習一下.. 有機會再和大家分享

Hope you find it useful