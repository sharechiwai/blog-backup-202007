---
id: 2138
title: 'Setup Git for BitBucket on Windows Part I &#8211; 在Windows 上設定Git Part I'
date: 2011-11-07T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2138
permalink: '/2011/11/setup-git-for-bitbucket-on-windows-%e5%9c%a8windows-%e4%b8%8a%e8%a8%ad%e5%ae%9agit/'
categories:
  - Experience Share / 經驗分享
---
開始使用**BitBucket**

大家可以到以下網址登記和開始使用  
 <a href="https://bitbucket.org/plans" target="_blank">https://bitbucket.org/plans</a>

登記好之後我們使可以開始安裝git了  
大家可以到以下網址Download  
 <a title="Download msysgit" href="http://code.google.com/p/msysgit/downloads/list" target="_blank">http://code.google.com/p/msysgit/downloads/list</a>

今天我選擇了 **Git-1.7.7.1-preview20111027.exe**  
當你們使用時已可能已經有新的程式..  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cb4639aa55bd428c9bf6dd3c033eb429" alt="Download msysgit" width="776" height="332" />  
**Download** 完成後 打開這個安裝程式之後按&#8221;**Next**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4a4360ee07774e9788bca20c2d5766f6" alt="Start to install Git" width="503" height="388" /> 

閱讀**License** 資料之後按&#8221;**Next**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/ca119b76a5c94a8a8d226aaec81bffd2" alt="License Agreement" width="503" height="388" />  
之後可以**選擇安裝位置**..之後按&#8221;**Next**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e3c8e528ff814f02a1f041d65b04bea2" alt="Install Folder" width="503" height="388" />  
選擇希望安裝的**Git**元件 -> 選擇默認的設定便可以了 [我uncheck了 &#8220;**Additional icons** -> **on Desktop**&#8221; 這個選項]  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8e0d99896ef347a08de8faab8b83127d" alt="Setup options" width="521" height="406" /> 

按&#8221;**Next**&#8221; 之後可以選擇 **Start Menu**中資料裡的名稱  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0ec99be0225e426c83ddb4c855cb9736" alt="" width="503" height="388" />  
設定環境變數&#8230; 選擇 &#8220;**Run Git from the Windows Command Prompt**&#8221;  
E.G. **commit**, **Update**, **Push**, **Pull** 程式碼..等等  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7deb63c454bc409994d4e6744c14cd4c" alt="Run Git from the Windows Command Prompt" width="503" height="388" /> 

由於我是使用**Windows** 的關係..所以我選擇 &#8220;**Checkout Windows-Style, commit Unit-style line endings**&#8221; 以便方便使用  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/960df48aef254d1c80e7a7a5de734b8c" alt="Checkout Windows-Style, commit Unit-style line endings" width="503" height="388" />  
安裝**Git**中  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1d3f2bd0041048ac81b77053440c8010" alt="Installing Git" width="503" height="388" />  
安裝完成了&#8230; 我們便要開始設定我們電腦上的**Git**了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f41044f7ec514116bfa26b1b2ced4e46" alt="Git Installation Completed" width="503" height="388" /> 

測試**Git**是不是成功安裝在你的電腦上可以嘗試以下方去  
打開&#8221;**Command Prompt**&#8221;  
執行以下指令  
&#8220;**git**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/557dfd699a514ad2af6b19e6702eb59f" alt="run git command" width="546" height="134" />  
如果**Git** 是成功完成安裝你應該可以看到以下畫面的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a11b8e0e37fe45c59e2f4e653bb3007f" alt="Git command working" width="678" height="305" /> 

我們現在可以使用**Git**了

由於這個post太長了..所以我分開了做PartII 有興趣的朋友可以參考以下的網誌  
<a title="Setup Git for BitBucket on Windows Part II – 在Windows 上設定Git Part II" href="http://blog.sharechiwai.com/2011/11/setup-git-for-bitbucket-on-windows-part-ii-%e5%9c%a8windows-%e4%b8%8a%e8%a8%ad%e5%ae%9agit-part-ii/" target="_blank">Setup Git for BitBucket on Windows Part II &#8211; 在Windows 上設定Git Part II</a>

Hope you find it useful