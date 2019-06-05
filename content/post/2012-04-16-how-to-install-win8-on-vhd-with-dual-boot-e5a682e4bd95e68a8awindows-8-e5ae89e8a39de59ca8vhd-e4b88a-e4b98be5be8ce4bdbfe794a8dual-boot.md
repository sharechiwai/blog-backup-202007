---
id: 2343
title: 'How to install Win8 on VHD with Dual Boot &#8211; 如何把Windows 8 安裝在VHD 上 之後使用Dual Boot'
date: 2012-04-16T00:00:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2343
permalink: '/2012/04/how-to-install-win8-on-vhd-with-dual-boot-%e5%a6%82%e4%bd%95%e6%8a%8awindows-8-%e5%ae%89%e8%a3%9d%e5%9c%a8vhd-%e4%b8%8a-%e4%b9%8b%e5%be%8c%e4%bd%bf%e7%94%a8dual-boot/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - VHD
  - VHD Dual Boot
  - Windows 8
---
把**Windows 8** 安裝在**VHD** 上 之後使用**Dual Boot**

聽起來很像很困難..  
但是事實上算是十分簡單的  
首先我們先要把**Windows 8**的**ISO** 燒錄到**DVD** 或 **USB**上

之後建立好一個**VHD**

建立VHD的詳情可以參考以下網誌

# <a title="Permalink to Windows 8 VHD Dual Boot Part 1 – How to Create Virtual Hard Drive (VHD) – 如果在Windows 上建立Virtual Hard Drive" href="http://blog.sharechiwai.com/2012/04/windows-8-vhd-dual-boot-part-1-how-to-create-virtual-hard-drive-vhd-%e5%a6%82%e6%9e%9c%e5%9c%a8windows-%e4%b8%8a%e5%bb%ba%e7%ab%8bvirtual-hard-drive/" rel="bookmark">Windows 8 VHD Dual Boot Part 1 – How to Create Virtual Hard Drive (VHD) – 如果在Windows 上建立Virtual Hard Drive</a>

或

# <a title="Permalink to Create VHD via DiskPart Command – 使用DiskPart來建立虛擬硬碟" href="http://blog.sharechiwai.com/2012/04/create-vhd-via-diskpart-command-%e4%bd%bf%e7%94%a8diskpart%e4%be%86%e5%bb%ba%e7%ab%8b%e8%99%9b%e6%93%ac%e7%a1%ac%e7%a2%9f/" rel="bookmark">Create VHD via DiskPart Command – 使用DiskPart來建立虛擬硬碟</a>

所有事情都預備好之後便可以開始安裝**Win8**了  
放入了**Windows 8**的**DVD** 光碟..之後開啟電腦  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4f4eb6c01cc842f0ac33b555939b3b6d" alt="Press any key to boot from CD or DVD.." width="455" height="74" />  
選擇**Windows 8**系統語言..  
之後按&#8221;**Next**/**下一步**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1e9143cb6bd5440fab76eea86be44455" alt="Windows Setup -> Select Language" width="726" height="524" />  
按&#8221;**Install Now**/**馬上安裝**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ca68957397e341eb8c1ff92d7f900ec8" alt="Install Now" width="651" height="506" /> 

之後便要輸入**Windows 8**的**Product Key**了  
輸入後按&#8221;**Next**/**下一步**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/265e358729184e7f87ce34ca5d2acd70" alt="Enter Windows 8 S/N" width="650" height="500" /> 

便要接受使用條款 ->按&#8221;**Next**/**下一步**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/82c97c8f8d794e2687de556fc0696057" alt="Accept the license terms" width="672" height="508" /> 

在&#8221;**Which type of installation do you want** /**那一個安裝種類**&#8221;  
選擇&#8221;**Custom: Install Windows Only (advanced)** / **自定: 安裝視窗**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/164e37e47a914b89af09dda9dfb22492" alt="Which type of installation do you want /那一個安裝種類" width="664" height="508" /> 

在&#8221;**Where do you want to install Windows**/ **那裡安裝視窗**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4ca5c712d1db4209bc58dc17565c7f0f" alt="Where do you want to install Windows/ 那裡安裝視窗" width="685" height="509" /> 

不用選擇任合一個 **Hard Drive**  
而按鍵盤&#8221;**SHIFT + F10**&#8216; 來使用 **Windows命令行**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0cb3caf988f448fbb6364dee01b7600d" alt="Windows Console" width="705" height="507" />  
之後我們需要使用**DiskPart**把之前建立的**VHD Attach** 到電腦上

首先我們要知道之前把這個VHD 儲存在那裡  
我們可以用**Dos Command** 來查  
E.G. **C:\ dir**等等

因為在這個安裝模式中..我們的硬碟位置有可以會和之前在Win7看到的不同  
之前我是**VHD** 是儲存在**E:**的  
而**Windows 7**是在**C:** 的  
現在位置都不同了  
我的**VHD** 是在**D:** 了

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2948042dde99412d9ccefbb3b0cbbc46" alt="Check where is the VHD to be attach" width="650" height="590" /> 

知道**VHD** 儲存在那裡我們便可以用Diskpart的指令來**Attach**這個**VHD**了  
E.G.  
輸入<span style="color: #008000;"><strong>DiskPart</strong></span>  
之後輸入以下指令選擇 **VHD**  
<span style="color: #008000;"><strong>select vdisk file=d:\VHD\Win8.vhd</strong></span>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a24ae7ef51954b18aa350be9ca043c5c" alt="Select VHD for Windows 8" width="510" height="185" />  
之後輸入以下指令**Attach VHD**  
<span style="color: #008000;"><strong>attach vdisk</strong></span>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ba6bd04c484b4163984ff9eff9aec67c" alt="attach VHD for windows 8" width="468" height="130" />  
完成後輸入 &#8220;<span style="color: #008000;"><strong>exit</strong></span>&#8221; 離開**DiskPart**  
之後關閉這一個**Windows Console**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/20b4792410924061bc9ac7c8de0882d2" alt="Exit Diskpart" width="223" height="86" />  
回到**Windows Setup** 看到硬碟上和之前沒有什麼分別  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4baacf16b15946eab35a9f3c06672ac4" alt="Hard Drive options unchanged" width="656" height="496" />  
我們以按一下&#8221;**Refresh**/**重新整理**&#8221;  
之後便會看到新增的 &#8220;**Drive**/**硬碟**&#8220; **Virtual Hard Disk**了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/460504c2ac92443aa6d4998d5807e4ae" alt="VHD appear after clicking in refresh" width="663" height="484" />  
我們選擇新增的**VHD**.. 之後按&#8221;**Next**/**下一部**&#8221;

有時候可能會有彈出一個錯誤信息  
E.G.  
&#8220;<span style="color: #ff0000;"><strong>Windows cannot be installed to this disk. This computer&#8217;s hardware may not support booting to this disk. Ensure that the disk&#8217;s controller is enabled in the computer&#8217;s BIOS menu</strong></span>&#8221;

如果這個情況出現的話而你又不能**Boot**到這個**VHD**上你便需要在**BIOS** 更改設定&#8230;Otherwise是可以不理會他的&#8230;

安裝開始了[之後我也沒有理會他..不久便安裝完成了]  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c25a619819d4483eae9ec7a41148f8c8" alt="Installing Windows 8" width="665" height="504" />  
**Getting Devices Ready**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8c2f90d6790247d6bfb7427ea25b8819" alt="Getting Devices Ready" width="628" height="522" />  
**Getting System Ready**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c9766e25ae7a4923a98572efcf657a4d" alt="Getting System Ready" width="483" height="535" />  
完成後便會看到**Dual Boot**的畫面  
大家可以選擇**Windows 8**或**Windows 7**  
或者是可以更變預設的設定  
&#8220;**Change default or choose other options**/**改變預設或選擇其他選擇**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/fb2ecfa70d4f408eb3d21f4466aa43b8" alt="Dual Boot Windows 8 in VHD" width="742" height="647" /> 

現在可以**Dual Boot** 在**VHD** 上的 **Win8** 或在正常硬體上的**Win7**了  
可以享受真實硬體的效能

Hope you find it useful