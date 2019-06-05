---
id: 3057
title: 'Android Exit Current Activity &#8211; 如何在Android 上用程式碼關閉現在的Activity'
date: 2014-02-23T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3057
permalink: '/2014/02/android-exit-current-activity-%e5%a6%82%e4%bd%95%e5%9c%a8android-%e4%b8%8a%e7%94%a8%e7%a8%8b%e5%bc%8f%e7%a2%bc%e9%97%9c%e9%96%89%e7%8f%be%e5%9c%a8%e7%9a%84activity/'
categories:
  - Android
tags:
  - Android Tips and Tricks
---
在之前的網誌和大家分享了  
<a title="Android detect / disable back press – 在Android上偵查/停用 如果用戶按下後退按鈕" href="http://blog.sharechiwai.com/2014/02/android-detect-disable-back-press-%E5%9C%A8android%E4%B8%8A%E5%81%B5%E6%9F%A5%E5%81%9C%E7%94%A8-%E5%A6%82%E6%9E%9C%E7%94%A8%E6%88%B6%E6%8C%89%E4%B8%8B%E5%BE%8C%E9%80%80%E6%8C%89%E9%88%95/" target="_blank">Android detect / disable back press – 在Android上偵查/停用 如果用戶按下後退按鈕</a>

停用了**Back press button** / **後退按鈕**

那麼我們可以怎樣才可以以在程式碼上退出現在的這個**Activity**呢?  
我們以建立一個**按鈕**/**Context Menu**等等的東西..  
讓使用者可以用來離開這個**Activity**/返回上一個**Activity**

做了一會資Research 之後發現..完來解決方法很簡單..

**解決方法:**  
我們可以使用 **finish()** 這個功能來實現  
E.G.

[java]  
finish();  
[/java]

Hope you find it useful