---
id: 2339
title: 'Create VHD via DiskPart Command &#8211; 使用DiskPart來建立虛擬硬碟'
date: 2012-04-15T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2339
permalink: '/2012/04/create-vhd-via-diskpart-command-%e4%bd%bf%e7%94%a8diskpart%e4%be%86%e5%bb%ba%e7%ab%8b%e8%99%9b%e6%93%ac%e7%a1%ac%e7%a2%9f/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Disk Management
  - DiskPart
  - VHD
  - Windows 8
---
首先我們需要使用**DiskPart**這個指令來建立這個**虛擬硬碟**  
所以我們要使用管理員身分執行**Command Prompt** [**命令提示字元**]  
&#8220;**Start**/**開始**&#8221; -> &#8220;**Accessories**&#8220;->在&#8221;**Command Prompt**/**命令提示字元**&#8220;上按 &#8220;**Mouse Right Click**&#8221; 之後選擇 &#8220;**Run as administrator**/**以管理員執行**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3a56d2f9e30b494fb8ac4b123b35a036" alt="Start-Accessories-Command Prompt" width="414" height="507" />  
之後我們可以在&#8221;**Command Prompt**/**命令提示字元**&#8220;上輸入以下指令  
<span style="color: #008000;"><strong>diskpart</strong></span>  
來使用**DiskPart**這個功能  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a2e9a40f970d420183643f25adc0ef01" alt="DiskPart Command" width="658" height="190" /> 

之後使用**create vdisk** 指令來建立我們可的**虛擬硬碟** 和一些基本的設定 如: **虛擬硬碟的種類**和 **最大的硬碟空間有多小**  
**create vdisk file=你想把這個虛擬硬碟建立到的位置 type=虛擬硬碟的種類 E.G. Fixed[Fixed-size VHDs.] | expandable [Dynamically expanding VHDs] | parent**  
 **[Differencing VHDs] 最後一個參數是空間最大是多小..單位是以MB 來設定的**  
詳情可以參考以下網頁  
 <a href="http://technet.microsoft.com/zh-cn/library/gg252579(v=ws.10).aspx" target="_blank">http://technet.microsoft.com/zh-cn/library/gg252579(v=ws.10).aspx</a>  
我們會使用的虛擬硬碟種類是 **Dynamically expanding VHDs** &#8220;**expandable**&#8221; 和用使用大概**80GB** 的空間  
使用種類&#8221;**expandable**&#8220;其中一個好處是雖然我們是想要80GB 的空間..當我們建立這個虛擬硬碟的時候..他的大小只會是有資料的時候才會增加&#8230;最大間空會被鎖定為80GB&#8230;  
所以我的指令會像以下這一句

<span style="color: #008000;"><strong>create vdisk file=E:\VHD\Win8.vhd type=expandable maximum=80000</strong></span>

之後我們可以檢查一下剛才建立的**VHD**..他的實際大小只有**159kb** [是不是很神奇呢?]

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2282e2cd8b044d8caa1b4573cbdfc568" alt="Check VHD just created" width="564" height="201" /> 

建立**VHD**後我們需要選擇剛建立的**VHD**&#8230;之後說明給電腦聽 我們要把這個**VHD Attach**到電腦上 才可以有效使用的

**選擇VHD**..我們可以使用這個指令  
<span style="color: #008000;"><strong>select vdisk file=E:\VHD\Win8.vhd</strong></span>

之後輸入以下指令把這個**VHD** 連接到電腦上  
<span style="color: #008000;"><strong>attach vdisk</strong></span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8eb4c54f0eac4b0f9b38a71e9363cab0" alt="Select and Attach VDisk VHD" width="481" height="149" />  
之後我們需要把這個**VHD** 變成**Primary Partition**以備將來使用  
我們可以輸入以下指令  
<span style="color: #008000;"><strong>create partition primary</strong></span>

完成後電腦使用彈出一個和硬碟有關的信息.. 說&#8221;**You need to format the disk in drive F: before you can use it**.&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/031336c5239d4464ac8241e5c045818b" alt="You need to format the disk in drive F: before you can use it." width="675" height="254" />  
這裡選擇&#8221;**Cancel**/**取消**&#8221;  
如果你按了**Format**他便會出現以下錯誤信息..  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3d2f153db97148f39d9b6594cb288d48" alt="Windows cant format VHD" width="367" height="206" /> 

之後你可以輸入指令來離開**DiskPart**這個指令  
和關閉**Command Prompt** [**命令提示字元**]  
<span style="color: #008000;"><strong>exit</strong></span>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c6d6d9d8ac2c49cea39d257cf8abe9be" alt="exit DiskPart Command" width="465" height="134" />  
**VHD** 便可以準備使用了

Hope you find it useful