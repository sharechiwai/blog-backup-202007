---
id: 23
title: 'Windows Live Messenger stop working &#8212; Windows Live Messenger 已經停止運作'
date: 2010-07-07T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=23
permalink: '/2010/07/windows-live-messenger-stop-working-windows-live-messenger-%e5%b7%b2%e7%b6%93%e5%81%9c%e6%ad%a2%e9%81%8b%e4%bd%9c/'
jabber_published:
  - "1281814640"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
最近常常看到 朋友的**MSN/ Windows Live Messenger出現問題**  
很多時候都是出現  
&#8220;<span style="color:#ff0000;"><strong>Windows Live Messenger 已經停止運作</strong></span>&#8221; 訊息  
在<span style="color:#008000;">Event Log事件檢視器</span> 會看到以下信息

**<span style="color:#ff0000;">失敗的應用程式 msnmsgr.exe，版本 14.0.8117.416，時間戳記 0x4bc935af，失敗的模組 WLDCore.dll，版本 14.0.8117.416，時間戳記 0x4bc93503，例外狀況碼 0xc0000005，錯誤位移 0x00002ee5， 處理程序識別碼 0x1654，應用程式開始時間 0x01cb32278ab8dc38。</span>**

最後終於找到了**解決方法**  
就是  
在&#8221;**開始**&#8220;->&#8221;**執行**&#8221;  
輸入 &#8220;**regedit**&#8221;  
按&#8221;確認&#8221;  
沿著路徑找到 &#8220;**HKEY\_CURRENT\_USERSOFTWAREMicrosoftMSNMessenger**&#8221;  
刪除 &#8220;**MSNMessenger**&#8221; 整個 subfolder ，  
重新啟動 **MSN/Windows Live Messenger** 就可以了

Hope you find it useful