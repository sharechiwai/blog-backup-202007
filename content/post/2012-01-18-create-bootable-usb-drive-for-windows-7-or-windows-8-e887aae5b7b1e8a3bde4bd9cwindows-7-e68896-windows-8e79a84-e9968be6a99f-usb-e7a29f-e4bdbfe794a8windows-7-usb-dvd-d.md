---
id: 2282
title: 'Create Bootable USB Drive for Windows 7 or Windows 8 自己製作Windows 7 或 Windows 8的 開機 USB 碟  [使用Windows 7 USB DVD Download Tool]'
date: 2012-01-18T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2282
permalink: '/2012/01/create-bootable-usb-drive-for-windows-7-or-windows-8-%e8%87%aa%e5%b7%b1%e8%a3%bd%e4%bd%9cwindows-7-%e6%88%96-windows-8%e7%9a%84-%e9%96%8b%e6%a9%9f-usb-%e7%a2%9f-%e4%bd%bf%e7%94%a8windows-7-usb-dvd-d/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Asus ZenBook UX31E
  - Windows 7 USB DVD Download Tool
---
之前因為公司買了一部新的Laptop **Asus ZenBook UX31E**&#8230;  
這些很Silm的Laptop因為要減輕重量的關係..所以是沒有DVD Rom的  
由於原裝的OS 是 **Windows 7 Home Premium Edition**的關係..  
而我希望可以使用**Windows 7 Professional Edition**  
所以便要想方法&#8230;  
使用USB 來做一個安裝媒體  
之前看過一些教學..要使用**Command Line**的**DiskPart**功能..  
所以比較煩..比較複雜&#8230;

幸好最後找到一個比較方便的方法&#8230;  
大家先要準備一個**USB Drive**..  
要有4GB 或以上的Free Space的.  
和一個**Windows 7**/**Windows 8**的 DVD的ISO 檔案..  
之後我們可以到**Microsoft Store**上 Download **Windows 7 USB DVD Download Tool**  
大家可以到以下URL Download和安裝  
[http://wudt.codeplex.com/](Windows%20USB/DVD Download Tool "http://wudt.codeplex.com/")  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/03e5b4c28bfe477cb0d0d1a00c5c1e71" alt="Windows 7 USB DVD Download Tool - System Requirement" width="760" height="334" /> 

安裝程序十分簡單  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ff7d332c40e64fa1b1b1d9cf5d134991" alt="Install Windows 7 USB DVD Download Tool" width="530" height="424" /> 

因為沒有什麼複雜的選擇&#8230;只要按&#8221;**Next**&#8221; -> &#8220;**Next**&#8220;便安裝完成了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3485d0aff0384f06b2b89ccc8bad598b" alt="Install Windows 7 USB DVD Download Tool Completed" width="541" height="435" /> 

安裝完成後 -> 大家可以按一下&#8221;**開始**/**Start**&#8221; ->選擇&#8221;**Windows 7 USB DVD Download tool**&#8221; -> 來程動程式  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ef2c55d139964253a592113aa8ae5ab1" alt="Start - Windows 7 USB DVD Download tool" width="424" height="139" /> 

第一個步驟是按一下&#8221;**Browse**&#8220;這個按鈕 ->選擇你之前準備好的Windows 7/ Windows 8 等等的ISO image&#8230;希望把他轉成 **Bootable USB Drive的 ISO **  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2e23b04d36b9422a823bc823601cd0ce" alt="Windows 7 USB DVD Download Tool Step1 Select ISO" width="619" height="334" />  
選擇了要複製的ISO 之後按 &#8220;**Next**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2b918b599eb1417788abe4d3d996344e" alt="Windows 7 USB DVD Download Tool Step1 Choose image" width="827" height="496" />  
在第二個步驟上我們可以選擇把這個ISO 複製到 **USB Device** 還是**DVD**&#8230;  
選擇**USB Device**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/71fa0252ac4e4428ab6338fdbfe83ef8" alt="Windows 7 USD DVD Download Tool - Choose Media Type - Select USD Device" width="625" height="346" />  
選擇好會用到的**USB Device**之後按一下&#8221;**Begin Copying**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8314d362c7da46728dab210731bd04c6" alt="Insert USB Device" width="603" height="342" />  
由於我的USB Drive上有內容的關係..所以他便彈出了一個信息說&#8221;**Not Enough Free Space**&#8220;..要**Format**這個USB Device&#8230;問我批不批准這個動作..  
選擇&#8221;**Yes**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e9d58d1c9aac4774a115b6a63fd2e35d" alt="Because the USB is not empty, it asked if it is ok to erase the data" width="614" height="375" />  
格式化我的USB Device中  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/efda4a482e864af2965dd12f254d06df" alt="Windows 7 USD DVD Download Tool - Choose Media Type - Formatting" width="638" height="358" />  
複製檔案中&#8230;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e4e4d0cf51464119826e9e26ad19262b" alt="Windows 7 USD DVD Download Tool creating Bootable USB Device" width="647" height="345" /> 

經過 15-20分鐘的時間 我的 **Windows 8 Bootable USB Device** 大功告成了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3d2cd74aa70c43569e9d3803a3b7f674" alt="Bootable USB Drive Created Successfully" width="596" height="335" /> 

現在可以開啟這個**USB Device**看看入面有什麼檔案  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/382267c445cd453e9e2fb8a122cf57e8" alt="USD Device content" width="802" height="342" /> 

完成!!!

Hope you find it useful