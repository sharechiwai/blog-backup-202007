---
id: 2330
title: 'Windows 8 VHD Dual Boot &#8211; Install Windows 8 on to VHD and Dual Boot Part 0  &#8211; Windows 8 安裝在VHD(Virtual Hard Disk)'
date: 2012-04-12T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2330
permalink: /2012/04/windows-8-vhd-dual-boot-install-windows-8-on-to-vhd-and-dual-boot-part-0/
categories:
  - Windows 8
tags:
  - Backup Boot Manager Database
  - VHD Dual Boot
---
最近上了一個有關**Windows 8 應用開發的活動**  
之後對**Windows 8**的**Application**開發十分有興趣

所以便希望可以在**Win7**上安裝一個**Virtual Machine**用來測試這一個Windows 8  
很可惜..  
暫時(2012年4月)很像還沒有一個可以做到在**Virtual Machine**上安裝了**Windows 8**又可以使用**Full Screen**的  
在**Virtual Box** 安裝完成後便變成了這樣子了.

**Full Screen Mode**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/76e7be95003c4e62bb989103ce2c81f5" alt="Windows 8 in Virtual Box Full Screen Scale Mode" width="1366" height="767" />  
**Scale Mode **  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/59510b91ad7e48e997b4615e4694ae85" alt="Windows 8 in Virtual Box Maximum with Normal Mode" width="1366" height="768" />  
感覺很不順暢呢

但是又不希望使用**Dual Boot**&#8230; 如果使**用Dual Boot**的話便要把**Hard Drive**做**硬碟分割 Partition**了&#8230;  
所以比較麻煩..還有要預留給**Windows 8**的**硬碟空間也不能用**..  
Just In case 這個**Windows** 有什麼問題.便會失去資料了

最後朋友介紹了我去參考**Hanselman**的博客..學習了如何把**Windows 8 安裝在VHD(Virtual Hard Disk)**上  
 [http://www.hanselman.com/blog/HowToGuideToInstallingAndBootingWindows8ConsumerPreviewOffAVHDVirtualHardDisk.aspx](http://www.hanselman.com/blog/HowToGuideToInstallingAndBootingWindows8ConsumerPreviewOffAVHDVirtualHardDisk.aspx "http://www.hanselman.com/blog/HowToGuideToInstallingAndBootingWindows8ConsumerPreviewOffAVHDVirtualHardDisk.aspx")  
把系統[**Windows 8**]安裝在**VHD**上的好處是可以令到使用者體驗到把**Windows 8安裝到真正硬體上的一樣..可以享受真實硬體的效能**..

把整個過程完成後  
系統便會出現一個**Dual Boot**的版面了&#8230;  
給用戶選擇**Windows 8** 或**Windows 7**  
最大的分別是我們的**Windows 8** 是安裝在一個**VHD**上  
而不是電腦上其中一個真實的Partition.  
<span style="color: #ff0000;"><strong>*免責聲明-以下只是我個人經驗分享&#8230;所以不能保証沒有風險的</strong></span>

如果大家有興趣的話可以參考以下我看完了**Hanselman** 之後以自己使用時遇到的經驗所寫的分享

首先我們要先確正我們硬碟有足夠的空間&#8230;(最小要有**40GB Free**的)  
之後我們要**Download Windows 8** 的**ISO**.. 之後把這個**ISO** 燒錄到**DVD** 或 **USB**上  
大家可以到 以下URL Download **Windows 8 Consumer Preview**  
<http://windows.microsoft.com/en-CA/windows-8/iso>

如果大家對把這個**ISO** 燒錄到**DVD** 或 **USB**上有困難可以參考以下網誌

# <a title="Permalink to Create Bootable USB Drive for Windows 7 or Windows 8 自己製作Windows 7 或 Windows 8的 開機 USB 碟  [使用Windows 7 USB DVD Download Tool]" href="http://blog.sharechiwai.com/2012/01/create-bootable-usb-drive-for-windows-7-or-windows-8-%e8%87%aa%e5%b7%b1%e8%a3%bd%e4%bd%9cwindows-7-%e6%88%96-windows-8%e7%9a%84-%e9%96%8b%e6%a9%9f-usb-%e7%a2%9f-%e4%bd%bf%e7%94%a8windows-7-usb-dvd-d/" rel="bookmark">Create Bootable USB Drive for Windows 7 or Windows 8 自己製作Windows 7 或 Windows 8的 開機 USB 碟 [使用Windows 7 USB DVD Download Tool]</a>

之後**備份**我們的**Boot Manager Database**, 因為使用**Dual Boot會改變硬碟上的 Boot Manager Database的**

**備份Boot Manager Database** 我們需要以**管理員身分執行Command Prompt** [**命令提示字元**]  
&#8220;**Start**/**開始**&#8221; -> &#8220;**Accessories**&#8220;->在&#8221;**Command Prompt**/**命令提示字元**&#8220;上按 &#8220;**Mouse Right Click**&#8221; 之後選擇 &#8220;**Run as administrator**/**以管理員執行**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3a56d2f9e30b494fb8ac4b123b35a036" alt="Start-Accessories-Command Prompt" width="414" height="507" />  
之後輸入以下指令 去 **Backup Boot Manager Database**  
指令是這樣的  
**BCDEDIT /export** [**在這裡輸入想把Boot Manager Database備份到的資料夾和檔案名**]

**E.G.**  
<span style="color: #008000;"><strong>BCDEDIT /export e:\VHD\bcdbackup_20120330.bak</strong></span>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/625d040f5cbe4e03ac41bdfc68fcfc8f" alt="Back up Boot Manager Database file command" width="594" height="144" /> 

完成後我們可以開啟備份到的資料夾看看所備份的檔案..之後可以Email 自己留多一個Copy/Backup  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/568da134e6f34dd0abe7b851787ca165" alt="Backed up Boot Manager Database file" width="372" height="161" />  
如果將來想還原 Boot Manager Database的話.可以使用還原的**Command**  
**BCDEDIT /import** [**在這裡輸入想把Boot Manager Database之前備份到的檔案和位置**]  
E.G.  
<span style="color: #008000;"><strong>BCDEDIT /import e:\VHD\bcdbackup_20120330.bak</strong></span>  
這個指命通常是你不想再使用這個**VHD Dual Boot**時執行的..執行之後重啟電腦便可以了

之後我們可以開始建立我們的**Virtual Hard Drive** (**VHD**)了  
由于這篇網誌太長了&#8230;所以我便分開 幾部分&#8230;  
大家可以參考如何建立 **Virtual Hard Drive  
** 

# <a title="Permalink to Windows 8 VHD Dual Boot Part 1 – How to Create Virtual Hard Drive (VHD) – 如果在Windows 上建立Virtual Hard Drive" href="http://blog.sharechiwai.com/2012/04/windows-8-vhd-dual-boot-part-1-how-to-create-virtual-hard-drive-vhd-%e5%a6%82%e6%9e%9c%e5%9c%a8windows-%e4%b8%8a%e5%bb%ba%e7%ab%8bvirtual-hard-drive/" rel="bookmark">Windows 8 VHD Dual Boot Part 1 – How to Create Virtual Hard Drive (VHD) – 如果在Windows 上建立Virtual Hard Drive</a>

**或  
** 

# <a title="Permalink to Create VHD via DiskPart Command – 使用DiskPart來建立虛擬硬碟" href="http://blog.sharechiwai.com/2012/04/create-vhd-via-diskpart-command-%e4%bd%bf%e7%94%a8diskpart%e4%be%86%e5%bb%ba%e7%ab%8b%e8%99%9b%e6%93%ac%e7%a1%ac%e7%a2%9f/" rel="bookmark">Create VHD via DiskPart Command – 使用DiskPart來建立虛擬硬碟</a>

當**Virtual Hard Drive** 建立好之後我們可以開始安全我們的**Windows 8**在這個**VHD**上  
詳情大家可以參考如何在把**Windows 8** 安裝在**VHD** 上 **Dual Boot  
** 

# <a title="Permalink to How to install Win8 on VHD with Dual Boot – 如何把Windows 8 安裝在VHD 上 之後使用Dual Boot" href="http://blog.sharechiwai.com/2012/04/how-to-install-win8-on-vhd-with-dual-boot-%e5%a6%82%e4%bd%95%e6%8a%8awindows-8-%e5%ae%89%e8%a3%9d%e5%9c%a8vhd-%e4%b8%8a-%e4%b9%8b%e5%be%8c%e4%bd%bf%e7%94%a8dual-boot/" rel="bookmark">How to install Win8 on VHD with Dual Boot – 如何把Windows 8 安裝在VHD 上 之後使用Dual Boot</a>

** **

Hope you find it useful