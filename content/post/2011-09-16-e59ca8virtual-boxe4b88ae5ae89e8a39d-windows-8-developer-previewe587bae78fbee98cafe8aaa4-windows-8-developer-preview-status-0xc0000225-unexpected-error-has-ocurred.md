---
id: 2078
title: '在Virtual Box上安裝 Windows 8 Developer Preview出現錯誤 &#8211; Windows 8 Developer Preview status: 0xc0000225 Unexpected error has ocurred'
date: 2011-09-16T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2078
permalink: '/2011/09/%e5%9c%a8virtual-box%e4%b8%8a%e5%ae%89%e8%a3%9d-windows-8-developer-preview%e5%87%ba%e7%8f%be%e9%8c%af%e8%aa%a4-windows-8-developer-preview-status-0xc0000225-unexpected-error-has-ocurred/'
categories:
  - Windows
tags:
  - Virtual Box
  - Windows 8
---
**Windows 8 Devloper Preview** 終於可以Download 了  
身為一個Developer 嘗然要安裝 &#8220;**Windows Developer Preview with developer tools English, 64-bit (x64)**&#8221;  
可以嘗試  
**Microsoft Visual Studio 11 Express for Windows Developer Preview**  
**Microsoft Expression Blend 5 Developer Preview**

誰不知在Virtual Box上安裝 **Windows 8 Developer Preview With Developer Tools** 出現錯誤  
&#8221;  
<span style="color: #ff0000;"><strong>Windows failed to start. A recent hardware or software change might be the cause.</strong></span>

<span style="color: #ff0000;"><strong>Status: 0xc0000225</strong></span>  
<span style="color: #ff0000;"><strong> Info: An unexcepted error has occurred.</strong></span>  
&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/630eb4dd01d54d359d8110bb6aec515b/renditions/fullsize.jpg?w=625" alt="windows 8 Status: 0xc0000225" data-recalc-dims="1" /> 

起初我還以為是我Download的**ISO** 出現問題..  
[因為同一時間我也Download了 **Windows 8 Developer Preview** &#8211; 沒有Developer Tools 的版本是可以順利安裝的]  
所以我最後再次download &#8220;**Windows Developer Preview with developer tools**&#8221;  
問題還是存在..  
之後便想應該是**Virtual Machine** 的設定問題了..  
最後經過多次嘗試..終於找到了解決方法..

**解決方法**:  
開啟**Virtual Box** 上**Windows 8 Instance** 的  
按滑鼠右鍵..  
之後選擇&#8221;**Settings…/設定&#8230;**&#8221;

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cf134210381149c0b285a031df2c4ad6/renditions/fullsize.jpg?resize=625%2C220" alt="Virtual Box Settings" width="625" height="220" data-recalc-dims="1" /> 

選擇&#8221;**System/系統**&#8220;分頁  
在預設的情況下  
&#8220;**Extended Features:**&#8221; 中的 &#8220;**Enable IO APIC**&#8221; 應該是沒有被選擇的  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ea866b82172f42828440493646e26370/renditions/fullsize.jpg?resize=625%2C468" alt="did not enabled IO APIC" width="625" height="468" data-recalc-dims="1" />  
只要我們**啟用**了&#8221;**Enable IO APIC**&#8221; 便可以解決這個問題  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/da7626481a9f4e7f90c0b1932e0937ed/renditions/fullsize.jpg?resize=625%2C470" alt="Enable IO APIC" width="625" height="470" data-recalc-dims="1" />  
成功啟動電腦到安全 &#8220;**Windows Developer Preview with developer tools**&#8221; 的畫面了

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2529c3dd015d4c6b90734178c6c2cfdd/renditions/fullsize.jpg?resize=625%2C522" width="625" height="522" alt="Setting up Windows 8 Developer Preview" data-recalc-dims="1" />  
Hope you find it useful