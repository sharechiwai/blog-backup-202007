---
id: 3053
title: 'Android detect / disable back press &#8211; 在Android上偵查/停用 如果用戶按下後退按鈕'
date: 2014-02-01T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3053
permalink: '/2014/02/android-detect-disable-back-press-%e5%9c%a8android%e4%b8%8a%e5%81%b5%e6%9f%a5%e5%81%9c%e7%94%a8-%e5%a6%82%e6%9e%9c%e7%94%a8%e6%88%b6%e6%8c%89%e4%b8%8b%e5%be%8c%e9%80%80%e6%8c%89%e9%88%95/'
categories:
  - Android
tags:
  - Android Tips and Tricks
---
很多時候 在**Mobile** / **Android Apps** 上  
當你按 **Back Button** 時 Apps 都會有一個彈出信息問..  
&#8220;**你是否真的想離開這程式嗎?**&#8221;

那麼這個效果是怎樣做的呢

原來我們可以<span style="color: #ff0000;"><strong>@Override OnBackPress</strong></span>這個 Method  
當用戶按Back Button 時這個功能便會觸發

如果要**Disable BackButton**我們可以使用以下的程式碼  
E.G.

[java]

@Override  
public void onBackPressed() {  
// 加入Return 便可以令他取消原本設定的動作/ 行為 [返回上一個Activity]  
return;  
}  
[/java]

Hope you find it useful