---
id: 3022
title: 'Android &#8211; How to go back to the previous activity who started your current activity via code &#8211; 在Android 上怎樣可以用程式碼來把程式回到之前的Activity 上'
date: 2014-01-27T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3022
permalink: '/2014/01/android-how-to-go-back-to-the-previous-activity-who-started-your-current-activity-via-code-%e5%9c%a8android-%e4%b8%8a%e6%80%8e%e6%a8%a3%e5%8f%af%e4%bb%a5%e7%94%a8%e7%a8%8b%e5%bc%8f%e7%a2%bc/'
categories:
  - Android
---
開始開發**Android Application** 時遇到了很多低階的開發問題&#8230;  
所以請用這個網誌幫自己記下這些解決方法..

**Android &#8211; How to go back to the previous activity who started your current activity via code &#8211; 在Android 上怎樣可以用程式碼來把程式回到之前的Activity** 上?

做了一會兒 research 之後有網友說可以使用 **finishActivity()** 來回到之前的**Activity**..  
可惜我試了.但是不知道為什麼不成功..  
可能我的程式上有些東西忘了設定

最後找到了另一個解決方法

**解決方去..**  
我們可以使用 **onBackPressed()** 這個方法來實現  
E.g.

[java]  
onBackPressed();  
[/java]

Hope you find it useful