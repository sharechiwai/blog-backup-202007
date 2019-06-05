---
id: 2243
title: 'XMLHttpRequest cannot load &#8211;  Origin is not allowed by Access-Control-Allow-Origin.'
date: 2012-04-01T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2243
permalink: /2012/04/xmlhttprequest-cannot-load-origin-is-not-allowed-by-access-control-allow-origin/
categories:
  - Experience Share / 經驗分享
---
今天在一個主題是使用主辦單位的**API** 的**Hack Event**上 出現了一個趣事&#8230;  
就是其中一個API 出現了很多的問題&#8230;  
相信他們是沒有真正的測試過便開放了這一個Beta給開發人員使用..  
其中一個問題是他們提供的**SandBox** URL 不是正確的  
另一個問題是使用者/開發者的帳戶&#8230;和API Key 很像沒有和**SandBox** 連結在一起..  
當使用使用者/開發者的帳 的API Key 時不能使用這個API&#8230;  
最後..我只可以使用Sample Code上的URL&#8230;

誰不知..當我準備好..了解他的**Function**和**Data Structure**時&#8230;  
正開始開發時..又出現一個很嚴重的問題  
就是當我當試使用**JQuery** 的 **$.getJSON** 功能來 取資料時&#8230;  
頁面沒有顯示任何資料..  
當我使用**Google Chrome**的 **Debugging Console** 看看有沒有任何錯誤信息時  
發現以下的錯誤資訊  
&#8220;<span style="color: #ff0000;"><strong>XMLHttpRequest cannot load http://api.europeandirectories.com/search.json?country=NL&what=pizza&where=Amsterdam&userid=portaluser&apikey=8f989d50f277c5ec3b9e890d497be820. Origin http://localhost:8080 is not allowed by Access-Control-Allow-Origin.</strong></span>&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7cae798e98f24317b689bc08ca8e555a" alt="error:  Origin http://localhost:8080 is not allowed by Access-Control-Allow-Origin." width="581" height="391" /> 

聽說這是一個和**Cross-domain** 想關的的問題&#8230;  
API 的Provider 需要在他們的Server/Service上更改一些設定來解決這個問題

另一個解決方法是使用**JSONP** &#8230;  
但是如果API 是沒有Implement JSONP的時候..你便沒有辦法了&#8230;

很可惜這個API 真是在一個很Beta的 Stage&#8230;所以還是沒有JSONP 的&#8230;

幸好最後有一個負責這個 API的開發人員 介紹了一個  
暫時的**解決方法**:  
就是啟動 **Google Chrome時 停用他的網路安全 設定**

大家可以按&#8221;**開始/Start**&#8221; -> &#8220;**執行/Run**&#8221;  
之後輸入以下文字  
**chrome.exe &#8211;disable-web-security**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/83613409e0414b488fdb505b8a7b8762" alt="run command chrome.exe --disable-web-security to bypass Origin is not allowed by Access-Control-Allow-Origin" width="429" height="247" />  
之後按&#8221;**確定/OK**&#8221;

當我再次嘗試這個Test Page時 便可以顯示資料了

Hope you find it useful.