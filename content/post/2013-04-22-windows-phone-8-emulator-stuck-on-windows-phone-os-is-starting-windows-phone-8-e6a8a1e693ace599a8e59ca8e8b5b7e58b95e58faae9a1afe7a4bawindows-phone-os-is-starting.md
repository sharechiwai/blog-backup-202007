---
id: 2792
title: 'Windows Phone 8 Emulator stuck on Windows Phone OS is starting&#8230; &#8211; Windows Phone 8 模擬器在起動只顯示Windows Phone OS is starting&#8230;便停了下來'
date: 2013-04-22T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2792
permalink: '/2013/04/windows-phone-8-emulator-stuck-on-windows-phone-os-is-starting-windows-phone-8-%e6%a8%a1%e6%93%ac%e5%99%a8%e5%9c%a8%e8%b5%b7%e5%8b%95%e5%8f%aa%e9%a1%af%e7%a4%bawindows-phone-os-is-starting/'
categories:
  - Window Phone Development
tags:
  - troubleshooting
---
最近繼續開始 **Windows Phone 8** 的開發了&#8230;  
把**Windows Phone 8 SDK** 安裝好之後..有一段時間都沒有理會他了  
[因為最近**Travel**比較多..所以很小**Coding**]

誰不知..當我嘗試開發**Windows Phone 8**的**Debug**時候..  
執行  
我的**Windows Phone 8**的 **Emulator** 在起動的畫面停下了&#8230;  
只是顯示著  
&#8220;<span style="color: #ff0000;"><strong>Windows Phone OS is starting&#8230;</strong></span>&#8220;的畫面&#8230;  
[<img class="alignnone size-full wp-image-2793" alt="The Windows Phone OS Is Starting" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TheWindowsPhoneOSIsStarting.jpg?resize=483%2C773" width="483" height="773" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TheWindowsPhoneOSIsStarting.jpg)

嘗試了Research很久也找不到解決方法..  
有人說..是我的電腦硬件不夠強..  
所以沒有能力推動**Windows Phone 8**的 **Emulator**  
之後我便到**MSDN Windows Phone 8** 的**SDK** 硬件要求要什麼&#8230;  
<a title="Windows Phone 8 System Requirement" href="http://msdn.microsoft.com/en-us/library/windowsphone/develop/ff626524(v=vs.105).aspx" target="_blank">http://msdn.microsoft.com/en-us/library/windowsphone/develop/ff626524(v=vs.105).aspx</a>

我使用的是 **ASUS UX31 i7** 有 **4GB RAM**&#8230;行**Windows 8 Pro Edition**的..  
所以應該是沒有問題的&#8230;

**解決方法**:  
到最後便嘗試使用 &#8220;**控制台** / **Control Panel**&#8221; -> &#8220;**Program and Features**&#8221; -> 之後選擇 **Windows Phone 8 SDK** 之後按 &#8220;**修復**/**Repair**&#8221;

&#8220;**修復**/**Repair**&#8221; 完成後便解決了問題.. 可以執行 **Windows Phone 8 Emulator** 了

Hope you find it useful