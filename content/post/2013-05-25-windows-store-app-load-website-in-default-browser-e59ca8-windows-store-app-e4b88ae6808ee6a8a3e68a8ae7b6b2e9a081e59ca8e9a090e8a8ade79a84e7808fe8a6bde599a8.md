---
id: 2917
title: 'Windows Store App Load Website in Default Browser &#8211;  在 Windows Store App 上怎樣把網頁在預設的瀏覽器上開啟'
date: 2013-05-25T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2917
permalink: '/2013/05/windows-store-app-load-website-in-default-browser-%e5%9c%a8-windows-store-app-%e4%b8%8a%e6%80%8e%e6%a8%a3%e6%8a%8a%e7%b6%b2%e9%a0%81%e5%9c%a8%e9%a0%90%e8%a8%ad%e7%9a%84%e7%80%8f%e8%a6%bd%e5%99%a8/'
categories:
  - Windows Store Apps
---
今天需要在**Windows Store App** 上加一個功能讓使用者按下按鈕後 會開啟一個網頁.

解決方法十分簡單.. 我們可以使用 **Launcher** 的 **LauchUriAsync**來實現這個動作

**解決方法**

[csharp]  
Launcher.LaunchUriAsync(new Uri("http://sharechiwai.com"));  
[/csharp]

Happy Coding