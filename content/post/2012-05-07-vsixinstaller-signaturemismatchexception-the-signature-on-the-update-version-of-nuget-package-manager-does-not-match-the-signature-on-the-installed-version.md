---
id: 2457
title: 'VSIXInstaller.SignatureMismatchException: The signature on the update version of &#8216;NuGet Package Manager&#8217; does not match the signature on the installed version.'
date: 2012-05-07T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2457
permalink: /2012/05/vsixinstaller-signaturemismatchexception-the-signature-on-the-update-version-of-nuget-package-manager-does-not-match-the-signature-on-the-installed-version/
categories:
  - Visual Studio
tags:
  - NuGet
---
今天嘗試使用**NuGet Package Manager**來下載和安裝 **MVVM Light ToolKits** 時  
出現了一段信息&#8230;說要Download的 **MvvmLight Package**的版本和我現在安裝了的**NuGet Package Manager**版本不相容&#8230; 我需要到 以下網址升級我的**NuGet**

&#8220;<span style="color: #ff0000;"><strong>The schema version of &#8216;MvvmLight&#8217; is in compatible with version 1.2.20325.9024 of NuGet. Please upgrade NuGet to the latest version from http://go.microsoft.com/fwlink/?LinkId=213942</strong></span>&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b39ae67d7f054f9db82a2d6de5b25abe" alt="" width="345" height="290" /> 

按了網址後他會把網址Redirect到 <a title="NuGet.Org" href="http://NuGet.Org" target="_blank"><strong>NuGet.Org</strong></a>  
之後選擇安裝 **NuGet**的時候 便會 Redirect 到 &#8220;**Visual Studio Gallery**&#8221; 的網址了

<a title="NuGet Visual Studio Gallery" href="http://visualstudiogallery.msdn.microsoft.com/27077b70-9dad-4c64-adcf-c7cf6bc9970c" target="_blank">http://visualstudiogallery.msdn.microsoft.com/27077b70-9dad-4c64-adcf-c7cf6bc9970c</a>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ba446e95df014d67adaaea45428c038f" alt="Visual Studio Gallery NuGet" width="923" height="567" /> 

下載之後可以開始升級&#8221;**NuGet Package Manager**&#8221; 了

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/40cc7dac840648809d76e6869c387289" alt="" width="467" height="367" />  
之後按&#8221;**Install**&#8221; 開始安裝..  
誰不知&#8230; &#8220;**Installation Failed** / **安裝失敗**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7b88115509cc45798a10e0cc14e611aa" alt="" width="461" height="366" /> 

之後按了 &#8220;**View Install Log**&#8221; 看看 那裡出現問題&#8230; 發現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>VSIXInstaller.SignatureMismatchException: The signature on the update version of &#8216;NuGet Package Manager&#8217; does not match the signature on the installed version.</strong></span>&#8221;

做了一些Research 之後有朋友介紹 可以嘗試 在**Visual Studio** 的 &#8220;**Extension Manager**&#8221; 上**Uninstall NuGet**.. 之後再次Install 便可以解決的

所以我便在**Visual Studio 2010**的**Menu**上 選擇 &#8220;**Tools**&#8221; -> &#8220;**Extension Manager&#8230;**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ef43145b4b5f4e94a65be170690ce952" alt="Tools Extension Manager" width="420" height="317" />  
之後便會看到&#8221;**NuGet Package Manager**&#8221; 這個元件..

很可惜選擇他之後&#8221;**Uninstall**&#8221; 和 &#8220;**Disable**&#8220;的選項都 不能選擇  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/32bd7b1457ec452999f9442fd4219808" alt="&quot;Extension" width="947" height="279" /> NuGet Options disabled&#8221;/>

所以便要找另一個方法了.

再做了一些Research 後..  
發現這是**Visual Studio** 版本的問題..  
**Microsoft**有一個**HotFix** 是可以解決的

大家可以到以下網址去Download這個Hotfix  
**KB2581019 &#8211; Error when you update or install a signed VSIX extensions in Visual Studio 2010 SP1**  
<a title="KB2581019 - Error when you update or install a signed VSIX extensions in Visual Studio 2010 SP1" href="http://connect.microsoft.com/VisualStudio/Downloads/DownloadDetails.aspx?DownloadID=38654" target="_blank">http://connect.microsoft.com/VisualStudio/Downloads/DownloadDetails.aspx?DownloadID=38654</a>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0e7e825538914d0d82561dffc4619ad2" alt="KB2581019 - Error when you update or install a signed VSIX extensions in Visual Studio 2010 SP1" width="724" height="582" /> 

Download完後可以開始安裝 這個**Visual Studio** 的**HotFix KB2581019**

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7f67a64c2578490f88b8eb0078b80396" alt="Install HotFix KB2581019" width="534" height="497" /> 

安裝 **Hot Fix KB2581019** 中  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/83b9dbe25c724d0aacc05613b4390c2d" alt="Installing HotFix KB2581019" width="527" height="494" /> 

安裝 **Hot Fix KB2581019** 完成了

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9458f240e21b4acfa589a5332cb35281" alt="Software update KB2581019 has been installed" width="527" height="497" /> 

之後便可以再次安裝/升級 &#8220;**NuGet Package Manager**&#8221; 了

安裝了**HotFix**之後果然能夠成功安裝/升級&#8221;**NuGet Package Manager**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c43117451c044b4aa91726dba5f0e447" alt="Install Upgrade NuGet Package Manager In Visual Studio 2010 Ultimate Complete" width="477" height="363" /> 

之後再次使用 &#8220;**NuGet Package Manager**&#8220;去安裝 **MvvmLight Package**成功了..  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/464c827690884a179d5de1c6e3324f5a" alt="Select project to install MVVMLight Package from NuGet" width="491" height="523" /> 

安裝完成後要接受 &#8220;**License Agreement**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f9c5a1cd6bdd4526aaf5b3db65822538" alt="MvvmLight Toolits License Agreement" width="418" height="463" /> 

完成了

Hope you find it useful