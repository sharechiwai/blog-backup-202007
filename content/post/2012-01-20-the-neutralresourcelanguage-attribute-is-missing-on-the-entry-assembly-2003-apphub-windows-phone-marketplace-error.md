---
id: 2246
title: 'The [NeutralResourceLanguage] attribute is missing on the entry assembly (2003) &#8211; AppHub Windows Phone MarketPlace error'
date: 2012-01-20T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2246
permalink: /2012/01/the-neutralresourcelanguage-attribute-is-missing-on-the-entry-assembly-2003-apphub-windows-phone-marketplace-error/
categories:
  - Window Phone Development
tags:
  - .Net Troubleshooting
---
我的**AppHub Account**很快便會到期了..  
所以要快快把之前寫的一個程式的**Bug**解決之後再Republish..  
誰不知&#8230;當我**Package**好的時候..  
之後把這個**.xap** Upload 到**Marketplace**時出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>The [NeutralResourceLanguage] attribute is missing on the entry assembly (2003)</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/900b5e56a8a04a2ea95f5fef8de7c94d" alt="AppHub upload Marketplace error The [NeutralResourceLanguage] attribute is missing on the entry assembly (2003)" width="631" height="385" /> 

嘗我看到這個錯誤信息時..  
我突然間意想到..  
這可能和**Project Properties**有關的..  
更改了一些Settings之後問題的解決了

**解決方法**:  
在你的**Visual Studio**的 **Windows Phone**&#8220;**項目/Project**&#8220;上  
按右鍵&#8230;選擇&#8221;**內容/Properties**&#8221;  
之後選擇 &#8220;**應用程式/Application**&#8221;  分頁 -> 按一下&#8221;**Assembly Information&#8230;**&#8220;按鈕&#8230;  
之後你便可以看到&#8221;**Assembly Information**&#8221; 資訊了

預設的情況下 &#8220;**Neutral Language**&#8221; 的設定是 (none)的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8b74ebbf515c46c7824f21ee45d69fe3" alt="Default settings for Neutral Langauge on Project is (none)" width="451" height="409" /> 

我們可以使用 &#8220;**Neutral Language**&#8221; 上的Drop Down List 來選擇適當的語言

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ec7abda4a43c46e3865a576f09349307" alt="Assembly Information - set Neutral Language" width="471" height="576" /> 

完成之後按 &#8220;**確定/OK**&#8221;  
之後從新**Compile**你的程式..  
之後再次Upload 到 **AppHub Marketplace** 便可以了

Hope you find it useful