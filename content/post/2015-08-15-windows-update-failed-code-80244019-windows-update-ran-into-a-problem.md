---
id: 3489
title: Windows Update Failed Code 80244019 Windows Update ran into a problem
date: 2015-08-15T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3489
permalink: /2015/08/windows-update-failed-code-80244019-windows-update-ran-into-a-problem/
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Restore Windows Phone
  - Windows 8.1 Update
  - Windows Troubleshooting
---
今日嘗試做**Windows Update** 準備安裝 **Visual Studio 2015**時出現以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Code 80244019 Windows Update ran into a problem</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5666/20373641508_0fee08288c_z.jpg?resize=625%2C354" alt="Code 80244019 Windows Update ran into a problem" width="625" height="354" data-recalc-dims="1" />  
當我上網research 有什麼解決方法時..  
嚇了一跳.. 因為他建議我去**Safe Mode 安全模式**進行一次**掃毒**  
我在想.. 自己的**Windows 8** 好像沒有安裝 防毒軟件.. 只是依賴 **Windows 8**上的 **Windows Defender**  
不知道怎樣執行..  
幸好..再做深入一點Research後發現了另一個解決方法

**解決方法**十分簡單

我們要去 **Control Panel** -> **Windows Update**  
**E.G**.  
&#8220;<span style="color: #339966;"><strong>Control Panel\All Control Panel Items\Windows Update</strong></span>&#8221;

之後選擇&#8221;**Change Settings** / **更改設定**&#8221;

在 **Microsoft Update Section**  
不要Tick/勾取 &#8220;**Give me updates for other Microsoft products when I update Windows** / **更新時給我其他 Microsoft產品的更新** &#8221;  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5746/20373641418_9f5136b160_z.jpg?resize=625%2C390" alt="Give me updates for other Microsoft products when I update Windows / 更新時給我其他 Microsoft產品的更新" width="625" height="390" data-recalc-dims="1" />  
之後按 &#8220;**OK**/**確定**&#8221; 便會回到上一個畫面

之後按一下&#8221;**Try Again**/ **再試一次**&#8221; 或 &#8220;**Check for Update** / **檢查更新**&#8221;  
電腦便會檢查 只有和**Windows** 相關的更新來下載或安裝  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5705/20552716962_4efc640a24_z.jpg?resize=625%2C390" alt="Windows Update" width="625" height="390" data-recalc-dims="1" /> 

之後便可以下載更新了

Hope you find it useful