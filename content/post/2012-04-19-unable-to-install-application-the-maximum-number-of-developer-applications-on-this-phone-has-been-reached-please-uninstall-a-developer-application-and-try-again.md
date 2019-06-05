---
id: 2363
title: Unable to install application. The maximum number of developer applications on this phone has been reached. Please uninstall a developer application and try again
date: 2012-04-19T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2363
permalink: /2012/04/unable-to-install-application-the-maximum-number-of-developer-applications-on-this-phone-has-been-reached-please-uninstall-a-developer-application-and-try-again/
categories:
  - Window Phone Development
tags:
  - AppHub Account
---
今天嘗試發布自己開發的**Windows Phone 7**程式到手機上時出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Unable to install application. The maximum number of developer applications on this phone has been reached. Please uninstall a developer application and try again</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/76a9e07d4366418b88e2652f261a7c84" alt="Unable to install application. The maximum number of developer applications on this phone has been reached. Please uninstall a developer application and try again" width="755" height="124" />  
之前有聽過不同的**Subscription** 可以**Unlock** 和Deploy App的數量是不同的..亦都可以嘗試和**Microsoft**聯絡..他們可以增加**Device**/**Apps**的數量

**For Individual and Company accounts**:  
3 device unblocks  
10 apps per device

**For Student accounts**:  
1 device unlock  
10 apps per device

詳情可以參考以下URL  
 <a title="http://msdn.microsoft.com/zh-tw/library/hh202924(VS.92).aspx" href="http://msdn.microsoft.com/zh-tw/library/hh202924(VS.92).aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/hh202924(VS.92).aspx</a>

我明白自己**Deploy**到自己手機的程式數量只有2個..  
但是一知道為什麼還是出現這個錯誤信息..  
最後我把所有自己Deploy的程式都Uninstall了..  
很可惜..問題還是存在&#8230;

之後我嘗試使用**Windows Phone Developer Registration Tools** 去嘗試檢查一下會不會是手機 **Unlock**的問題

原來手機還是**registered**了的.所以應該不是**register**的問題  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8fc15c563ea6477b8d4c7c4c05c514bb" alt="This phone has already been registered. You may click 'Unregister' if you wish to unregister it." width="529" height="471" />  
或者嘗試再次**Unlock**試試看

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/23d636a445c2403597a794d9b3df6121" alt="If you unregister this phone you will no longer be able to use it with applications in development. Countinue?" width="717" height="506" /> 

成功**unregister**自己的手機之後再次去**Register**看看  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5d0b2ce16a2c4b7e8a17c6382cb33caa" alt="Your phone has successfully been unregistered" width="528" height="476" /> 

誰不知&#8230;我不能再**Developer Unlock**這部手機&#8230;  
在Unlock的時候出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Marketplace registration incomplete. Please return to the App Hub for more information (ErrorCode; 080043009)</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c36f39acf2d4400c8e54c22eacf29ca3" alt="Marketplace registration incomplete. Please return to the App Hub for more information (ErrorCode; 080043009)" width="523" height="480" /> 

登入到自己的**AppHub Account**便發現我的**App Hub Account** 不是**Active**了  
**Account Status**是 &#8220;**Pending**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/211f430def0546c385f5ff82d2194b00" alt="Account identity verification failed - Account Status: Pending" width="852" height="282" /> 

最後發現原來只有現在**Active**的**App Hub Account Unlock**了的手機才可以用來測試程式  
由於我要求**Refund &#8211; Auto-Renew** 了的**App Hub Account**所以 我的**Account Status** 是**Pending**  
亦都因為這樣所以我不能再Deploy Test App到我的手機上了..

最後我都解決了這個問題  
**解決方法**..  
找了一位有AppHub Account的 朋友幫我Developer Unlock我的手機便可以了

Happy Coding