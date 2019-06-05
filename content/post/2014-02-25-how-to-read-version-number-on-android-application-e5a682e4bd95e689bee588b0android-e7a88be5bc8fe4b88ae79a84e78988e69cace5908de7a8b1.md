---
id: 3061
title: 'How to Read version number on Android Application &#8211; 如何找到Android 程式上的版本名稱'
date: 2014-02-25T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3061
permalink: '/2014/02/how-to-read-version-number-on-android-application-%e5%a6%82%e4%bd%95%e6%89%be%e5%88%b0android-%e7%a8%8b%e5%bc%8f%e4%b8%8a%e7%9a%84%e7%89%88%e6%9c%ac%e5%90%8d%e7%a8%b1/'
categories:
  - Android
tags:
  - Android Tips and Tricks
---
今天開始寫自己的**Android App**上的 **About**/介紹 頁面&#8230;  
想在這裡放入**版本資訊.**..令使用者知道使用的是那一個版本..  
怎樣可以找出 自己的**Android App**上的**Version Name**/ **Version Code** / **版本名稱**呢?  
解決方法十分簡單

我們可以使用**getPackageManager**的**getPackageInfo**方法來找到 **Android App**的 **version name** / **version code** 等等的資料

**解決方法**

[java]  
//Version Name  
String versionName = getPackageManager().getPackageInfo(getPackageName(), 0).versionName;

// Version Code  
String versionCode = getPackageManager().getPackageInfo(getPackageName(), 0).versionCode;  
[/java]

Hope you find it useful