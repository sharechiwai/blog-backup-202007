---
id: 2073
title: 'PANIC: Could not open: C:\Users &#8211; Android could not start Emulator'
date: 2011-09-02T00:00:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2073
permalink: /2011/09/panic-could-not-open-cusers-android-could-not-start-emulator/
categories:
  - Android
---
今日又開始接觸**Android Programming**了  
有朋友找我幫他寫一個**慈善機構的Apps**  
由於是慈善機構的關係所以是沒有錢的..  
可能是沒有很多人會做沒有錢的事..  
所以他便找了我了..

對上一次寫**Android**的程式時已經是1年多之前了  
這是**Android**都是去到**1.6** 到**2.0**的時代..  
當我嘗試啟動 這個**Android Emulator** 時出現了以下的錯誤  
&#8220;<span style="color: #ff0000;"><strong>PANIC: Could not open: C:\Users\Chi&#8230;\.android/avd/demo.ini</strong></span>&#8221;

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ed16ec09ea02479e8f814b22f70582f1/renditions/fullsize.jpg?resize=625%2C446" alt="PANIC: Could not open: C:\Users" width="625" height="446" data-recalc-dims="1" /> 

由於我使用了 **Windows 7**/**Windows Vista** 的一個功能  
把我的**User Profile**從 &#8220;**C:\Users**&#8220;轉到 &#8220;**D:\UserProfile**&#8221;  
[這樣..每當我們要還原電腦 或 重新安裝電腦時..我們都不需要另外再Backup 自己的**User Profile**/ **My Document**等資料夾]  
而當我安裝好我的**Android Emulator** 後檔案和他的.ini 都是存在 &#8220;**D:\UserProfile**&#8220;上  
**Eclipse** 只會懂得找&#8221;**C:\Users**&#8221; 資料夾的關係&#8230;  
所以便找不到了  
做了一些reseach之後發現. 暫時為一個解決方法是把 &#8220;.android&#8221; 這個資料夾從&#8221;D:\UserProfile&#8221;

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/98c5e4fdc59c4f589b7b6013a70b540b/renditions/fullsize.jpg?resize=625%2C387" alt=".android folder on D:\Userprofile folder" width="625" height="387" data-recalc-dims="1" /> 

複製到  
&#8220;**C:\Users\Username\**&#8221; 上  
E.G.  
&#8220;**C:\Users\Chi&#8230;\**&#8221;

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/88703ecce6b544b1b7a8c5c24afa099d/renditions/fullsize.jpg?resize=625%2C375" alt=".android folder on C:\Users folder" width="625" height="375" data-recalc-dims="1" /> 

因為暫時&#8221;**Eclipse**/**AVD Manager**&#8221; 沒有一個選項可以改變執行路徑的

Hope you find it useful