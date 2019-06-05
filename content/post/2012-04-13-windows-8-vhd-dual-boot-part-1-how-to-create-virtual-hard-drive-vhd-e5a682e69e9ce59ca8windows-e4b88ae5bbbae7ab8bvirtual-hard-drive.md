---
id: 2337
title: 'Windows 8 VHD Dual Boot Part 1 &#8211; How to Create Virtual Hard Drive (VHD) &#8211; 如果在Windows 上建立Virtual Hard Drive'
date: 2012-04-13T00:00:40+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2337
permalink: '/2012/04/windows-8-vhd-dual-boot-part-1-how-to-create-virtual-hard-drive-vhd-%e5%a6%82%e6%9e%9c%e5%9c%a8windows-%e4%b8%8a%e5%bb%ba%e7%ab%8bvirtual-hard-drive/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Disk Management
  - VHD
  - Windows 8
---
我們可以開始建立我們的**Virtual Hard Drive** (**VHD**)了

建立虛擬硬碟 我們可以使用 **系統管理工具** 上的**電腦管理**->**磁碟管理** 的**GUI** 建立  
或者使用**Command Prompt**/**命令提示字元** 中的**DiskPart**指令來建立

在今天的教學..為了方便..所以會使用**電腦管理**->**磁碟管理** 的**GUI** 來建立  
首先我們先按&#8221;**Start**/**開始**&#8220;->&#8221;**Control Panel**/**控制台**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c465866f2af3450cbc3667d8772866d1" alt="Start->Control Panel" width="388" height="463" />  
開啟 &#8220;**Administrative Tools**/**系統管理工具**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/035d0c2363dd4f1bb5b79e67b96668b7" alt="Select Administrative Tools" width="594" height="239" />  
之後開啟&#8221;**Computer Management**/**電腦管理&#8221;**  
選擇&#8221;**Disk Management**/**磁碟管理&#8221;**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/bdeaa103c4fa478bb4b1f4af760b92ad" alt="Computer Management -> Disk Management section" width="573" height="193" />  
之後大家可以按一下&#8221;**Tool bar**/**工具欄**&#8220;上的&#8221;**Action**/**行動**&#8221; 之後選擇&#8221;**Create and Attach Virtual Hard Disk**&#8221;  
我們可以選擇將這一個**VHD** 儲存在那裡..  
按一下&#8221;**Browse&#8230;**&#8221; 按鈕..之後選擇想要儲存到的地方 輸入檔案名後按&#8221;**Save**/**儲存**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1958d56f4a464450a67ef29ec6beeb04" alt="browse where to store VHD" width="687" height="477" />  
之後選擇**VHD** 的大小.. 為了方便計算.. 大家可以按一下 選擇使用**GB** 代替 以**MB**計算  
之後選擇&#8221;**Dynamically expanding**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/248e73ca1d054a49afe1fb8c2771ff36" alt="Create and Attach Virtual Hard Disk - VHD settings" width="399" height="388" />  
最後按&#8221;**OK**/**確定**&#8221; 和開始建立**VHD**

完成後在&#8221;**Computer Management**/**電腦管理**&#8221; 上的&#8221;**Disk Management**/**磁碟管理**&#8221; 會見到一個新的**unknown**的硬碟..這就是剛才建立的**VHD**了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/580e291457c5469da5740999949461e8" alt="New VHD has been attached to Disk Management screen still need to initialise" width="801" height="424" />  
**VHD** 便可以準備使用了  
Hope you find it useful

大家可以參考怎麼安裝Windows 8 在VHD 上之後使用Dual Boot

# <a title="Permalink to How to install Win8 on VHD with Dual Boot – 如何把Windows 8 安裝在VHD 上 之後使用Dual Boot" href="http://blog.sharechiwai.com/2012/04/how-to-install-win8-on-vhd-with-dual-boot-%e5%a6%82%e4%bd%95%e6%8a%8awindows-8-%e5%ae%89%e8%a3%9d%e5%9c%a8vhd-%e4%b8%8a-%e4%b9%8b%e5%be%8c%e4%bd%bf%e7%94%a8dual-boot/" rel="bookmark">How to install Win8 on VHD with Dual Boot – 如何把Windows 8 安裝在VHD 上 之後使用Dual Boot</a>

&nbsp;