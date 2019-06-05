---
id: 2197
title: How to connect TFS Preview via Visual Studio 2010
date: 2011-11-22T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2197
permalink: /2011/11/how-to-connect-tfs-preview-via-visual-studio-2010/
categories:
  - Team Foundation Server
tags:
  - TFS Preview
---
今天開始嘗試使用**TFS Preview**  
在**TFS Preview Portal** 上建立了**Project**後才發現  
當我嘗試用**Visual Studio 2010**來連接 **TFS Preview** 時 便出現了以下的錯誤信息  
**TFS 的連接URL**是 你的&#8221;**TFS Preview Username.tfspreview.com**&#8221;  之後選擇 **HTTPS** 便可以

&#8220;<span style="color: #ff0000;"><strong>Team Foundation services are not available from server . Technical information (for administrator): HTTP code 203: Non-Authoritative Information</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/30c76cfdd86a44b28178d528a296da3a" alt="" width="669" height="423" /> 

經過一會兒的reseach之後..回想起在看**TFS Preview**的 **介紹影片**時&#8230;  
在影片中有提到&#8230;在**Visual Studio 2010**上需要安裝一些更新才可以用**Visual Studio**來連接 **TFS Preview**的  
之後我便找到**KB2581206** 這個更新了  
大家可以到以下URL Download 和安裝 [Visual Studio 2010需要有SP1 才可以安裝的]

<a title="KB2582306" href="http://go.microsoft.com/fwlink/?LinkID=212065" target="_blank">http://go.microsoft.com/fwlink/?LinkID=212065</a>

當我們Download完成後便可以安裝了.. 開啟程式後&#8230;安裝精靈便會出現&#8230;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/daadbe6e2d7a46a78218505a14691705" alt="Install Visual Studio 2010 Update KB2581206" width="519" height="490" />  
之後大家可以跟隨簡單的步驟按&#8221;**Next**&#8221; 和&#8221;**Install**&#8221;  
很快很方便..便可以完成安裝的

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/783a377214d444d2ae87380340359d74" alt="Software Update KB2581206 Installation Completed" width="517" height="485" /> 

當大家再次嘗試從**Visual Studio 2010**的 &#8220;**Connect to Team Server**&#8220;連接到&#8221;**TFS Preview**&#8221; 時 按下&#8221;**Connect/連接**&#8220;後便會出現以下的畫面  
&#8220;**Sign-In to Team Foundation Server**&#8221;  
之後他便會給你選擇 &#8220;**登入/Login**&#8220;的方法  
暫時很像只有 &#8220;**Windows Live ID**&#8221; 的選擇的  
按一下&#8221;**Windows Live ID**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b3c988bf821b4d4184cead79dc44693e" alt="Select Login Method for connection to TFS Preview" width="1026" height="659" /> 

之後便會出現&#8221;**Windows Live ID**&#8221; 的登入畫面  
填上了登入資料後按&#8221;**登入**&#8221; 便可以連接到你的&#8221;**TFS Preview**&#8221; Account了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f5b4398eb118494e83278b1225b8a157" alt="Login to Windows Live Account" width="1023" height="662" /> 

成功登入後便會把&#8221;**TFS Preview**&#8221; 的Server加進到 &#8220;**Team Foundation Server**&#8220;的 &#8220;**Team Foundation Server list**&#8221; 上  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1785ae8493c546438e32af62fef3214c" alt="Successfully connect to TFS Preview via Visual Studio 2010" width="658" height="419" /> 

sHope you find it useful =)