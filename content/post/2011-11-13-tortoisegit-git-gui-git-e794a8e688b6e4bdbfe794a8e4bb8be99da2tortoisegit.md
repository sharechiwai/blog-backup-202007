---
id: 2181
title: 'TortoiseGit &#8211; Git GUI &#8211; GIT 用戶使用介面TortoiseGit'
date: 2011-11-13T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2181
permalink: '/2011/11/tortoisegit-git-gui-git-%e7%94%a8%e6%88%b6%e4%bd%bf%e7%94%a8%e4%bb%8b%e9%9d%a2tortoisegit/'
categories:
  - Experience Share / 經驗分享
tags:
  - Git
---
如果不習慣使用**Command line**的**Git**的話  
可以安裝**TortoiseGit**  
他提供了使用者介面給用戶方便地使用Git

大家可以到以下URL Download/Install **TortoiseGit**  
<http://code.google.com/p/tortoisegit/downloads/list>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dd49bdac8e8440f1b3fc04810592058f" alt="URL to download tortoisegit" width="663" height="393" /> 

Download 了之後可以開啟剛才Download的程式 E.G. 我的版本是&#8221;**TortoiseGit-1.7.5.0-64bit.msi**&#8221;  安裝過程十分簡單, 大部份時間都是以預設的 設定  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9d0aa994f83d47b7a982e11ad044aea4" alt="Welcome to the TOrtoiseGIt" width="520" height="408" />  
之後按&#8221;**Next**&#8221; 去開始安裝  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/6262a8ebdc44449aa8efa9fc77866591" alt="Information about TortoiseGit" width="517" height="406" /> 

之後會看到 一差有關&#8221;**Terms and Condition**&#8221; 的資料..按&#8221;**Next**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/6e6199e91532473c85b54e0b750543db" alt="Tortoise Choose SSH Client" width="515" height="402" />  
由於我們在之前的教學中已經建立了SSH 的 **Public**和 **Private** Key 在選擇 &#8220;**SSH Client**&#8221; 的畫面上 選擇 &#8220;**OpenSSH, Git default SSH Client**&#8221; 之後按 &#8220;**Next**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/64ae3d70d5d4439ca266e0bac84613eb" alt="TortorseGit Custom Setup" width="514" height="404" /> 

在&#8221;**Custom Setup**&#8221; 畫面上可以 用預設的選項.. 或uncheck &#8220;**English (US) dictionary**&#8221; [由於不太佔用太多空間]..所以我選了預設的選項.之後按&#8221;**Next**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/876501b41baa4f309b16a1f9c0180d70" alt="TortouseGit The Setup Wizard is ready to begin the Custom Installation" width="519" height="407" /> 

把設定選擇好之後便可以按&#8221;**Install**&#8221; 開始安裝了

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/491199c87cf345e485ed28256ca910de" alt="Installing Tortoise" width="513" height="403" /> 

完成安裝了 可以按&#8221;**Finish**&#8221; 去關閉安裝程式

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/fb5e43dc2fdd45ef9566b65719201ca6" alt="TortoiseGit Installation Completed" width="516" height="409" /> 

測試我們有沒有成功安裝 &#8220;**TortoiseGit**&#8221;

我們可以建立一個&#8221;**資料夾**&#8221;  
之後在**資料夾**上按**Mouse Right Click**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/62fbe14a50b045edaacd5843c6a3ad0f" alt="TortoiseGit context menu" width="476" height="300" />  
之後大家便會看到一些和**Git**相關的 選項  
**E.G**.  
&#8220;**Git Clone**&#8221;  
&#8211; 用來Clone我們在Central Repository中其中一個 Repository  
&#8220;**Git Create repository here**&#8221;  
&#8211; 在這個資料夾上建立repository  
&#8220;**TortoiseGit**&#8221;  
&#8211; 可以看到更多和 TortoiseGit 相關的選項 E.G. Ssettings 和Help

我們先選擇 &#8220;**TortoiseGit**&#8220;->&#8221;**Settings**&#8221;  
在 &#8220;**TortoiseGit**&#8221; 的&#8221;**Settings**&#8221; 視窗上 選擇&#8221;**Git**&#8221; ->&#8221;**Config**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0f2e5a7d6a514b3eb2961f8fdb3ba2e6" alt="Setting->Git->Config&#8221; width=&#8221;717&#8243; height=&#8221;475&#8243; />  
之後把自己的**用戶名稱**和**Email** 填上 用來做一個使用者辨認的方法  
完成後按&#8221;**Apply**&#8221; 和&#8221;**OK**&#8221;

這樣我們便設定好我們的**TortoiseGit**了

在之後的網誌我們繼續記錄 如何建立**Repository** 和 **Commit** code到**Repository**上

Hope you find it useful  
待續&#8230;