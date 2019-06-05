---
id: 3369
title: 'How to Exit Application on Ionic &#8211; 如何在 Ionic 上 離開 / 關閉程式'
date: 2015-01-15T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3369
permalink: '/2015/01/how-to-exit-application-on-ionic-%e5%a6%82%e4%bd%95%e5%9c%a8-ionic-%e4%b8%8a-%e9%9b%a2%e9%96%8b-%e9%97%9c%e9%96%89%e7%a8%8b%e5%bc%8f/'
categories:
  - Ionic Framework
tags:
  - Hybrid App
---
如果想在 **Ionic Framework** 上自己寫一個**關閉程式**的制/ **功能**可以怎樣?

**解決方法**十分簡單  
我們可以使用以下的 程式碼便可以了

<pre>ionic.Platform.exitApp();
</pre>

e.g. 在**Controller**上

<pre>$scope.Quit = function(){
  ionic.Platform.exitApp();
}
</pre>

Hope you find it useful