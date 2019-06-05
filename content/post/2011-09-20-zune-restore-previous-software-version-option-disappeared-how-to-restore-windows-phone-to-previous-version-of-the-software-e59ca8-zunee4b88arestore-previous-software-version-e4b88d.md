---
id: 2086
title: 'Zune &#8211; Restore Previous Software Version option disappeared How to restore Windows Phone to Previous version of the software- 在 Zune上Restore Previous Software Version 不見了..'
date: 2011-09-20T00:00:40+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2086
permalink: '/2011/09/zune-restore-previous-software-version-option-disappeared-how-to-restore-windows-phone-to-previous-version-of-the-software-%e5%9c%a8-zune%e4%b8%8arestore-previous-software-version-%e4%b8%8d/'
categories:
  - Window Phone Development
tags:
  - Restore Windows Phone
  - Zune
---
最近看到已經有新出的**Windows Phone 7** 已經安裝了 **Mango**版本的**Operating System**..  
我在想&#8230;當**Samsung Omnia 7** 一出官方版本的時候..  
我便可以馬上更新了..  
由於現在手機上的**OS** 是**Developer Beta 2** [7712]版本的關係..  
要使用**原廠的ROM** 才可以使用原廠的更新  
所以我便要使用**Zune**來 **Restore**我的手機到**未有安裝Developer OS 的時候**了

誰不知&#8230;在&#8221;**Zune**&#8221; ->&#8221;**Settings**&#8220;->&#8221;**Phone**&#8220;->&#8221;**Update**&#8221; 這個選項上..  
&#8220;**Restore Previous Software Version**&#8221; 這個選項不見了  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dde9da1967ec41a2ae46edec72cb3b84/renditions/fullsize.jpg?resize=625%2C381" alt="Zune Restore Options Missing" width="625" height="381" data-recalc-dims="1" />  
之後查看&#8230;  
在&#8221;<span style="color: #3366ff;"><strong>C:\Users\Username\AppData\Local\Microsoft\Windows Phone Update\</strong></span>&#8221; 資料夾.. 看不到有之前**backup** 了的資料  
這可能是更新 **Zune**的時候資料夾被刪除造成的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/833204dc39e9485fb1ca13c0999ebbc5" alt="Could not find Windows Phone Backup Folder" width="745" height="468" /> 

幸好..之前自己**BackUp Windows Phone** 時已經把**Backup**檔複製到其他地方上..

<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/59eb5cdd91bf420ab4fbb3e8da54cbd9/renditions/fullsize.jpg?resize=625%2C272" alt="Zune My Own Windows Phone Backup Folder" width="625" height="272" data-recalc-dims="1" /> 

在**Backup Folder**上有2個資料夾用來儲存 用來**restore**手機原廠設定的資訊  
&#8220;**Property**&#8221; 和 &#8220;**RestorePoint**&#8221;

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/43f8a25468424f639b559fdf411478b9/renditions/fullsize.jpg?resize=625%2C271" alt="Windows Phone Backup Folder Properties and Restore Point" width="625" height="271" data-recalc-dims="1" /> 

**解決方法**:  
把已**Backup** 的資料夾複製到 &#8220;<span style="color: #3366ff;"><strong>C:\Users\Username\AppData\Local\Microsoft\Windows Phone Update\&#8221;</strong></span> 上  
之後重新開啟 **Zune**

再到&#8221;**Zune**&#8221; ->&#8221;**Settings**&#8220;->&#8221;**Phone**&#8220;->&#8221;**Update**&#8221; 這個選項上  
便可以看到**Restore**/**還原**這個選項了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4b3cb757d7e84996b4dbffcb1f8555b7/renditions/fullsize.jpg?resize=625%2C379" alt="Zune Windows Phone Restore options" width="625" height="379" data-recalc-dims="1" /> 

Hope you find it useful