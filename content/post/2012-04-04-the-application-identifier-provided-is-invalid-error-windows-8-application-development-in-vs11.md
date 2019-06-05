---
id: 2308
title: 'The application identifier provided is invalid. error &#8211; Windows 8 Application Development in VS11'
date: 2012-04-04T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2308
permalink: /2012/04/the-application-identifier-provided-is-invalid-error-windows-8-application-development-in-vs11/
categories:
  - Windows 8
tags:
  - VS11
---
今天在學習**Windows 8** 的**Application Development**  
在做到和**Push Notification** 相關的**exercise**時出現了  
當程式在**Debug Mode** 執行到**Push Notification** 相關的程式碼時  
**E.G.**

[csharp]  
//clear previous badge  
BadgeUpdateManager.CreateBadgeUpdaterForApplication().Clear();

// Register for badge notifications  
var channel = await PushNotificationChannelManager.CreatePushNotificationChannelForApplicationAsync();

[/csharp]

出現了以下的這個錯誤&#8230;  
&#8220;<span style="color: #ff0000;"><strong>The application identifier provided is invalid.</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5fac9aa788704a7ebddc016729fcdc2a" alt="The application identifier provided is invalid." width="486" height="414" />  
之後問了其他人也有遇過差不多的問題  
解決方法十分簡單

**解決方法**:  
只要大家在&#8221;**Windows 8 Simulator**/**Windows 8的模擬器**&#8221; **Uninstall** 正在開發中的**App**  
之後把&#8221;**Windows 8 Simulator**/**Windows 8的模擬器**&#8220;**關閉**  
大家可以在&#8221;**Task bar**/**任務欄**&#8221; 上按Mouse右鍵  
之後選擇&#8221;**Exit**/**離開**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a3479bca8afa4dd091fa5b021ab0a52c" alt="Exit Windows 8 Simulator" width="952" height="602" />  
之後再重啟你的**VS11**便可以了

如果還是有問題的話  
可以嘗試重新開啟電腦

Hope you find it useful