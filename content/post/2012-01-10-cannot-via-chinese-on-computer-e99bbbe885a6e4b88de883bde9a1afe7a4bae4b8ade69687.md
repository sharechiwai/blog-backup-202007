---
id: 2224
title: 'Cannot via Chinese on computer &#8211; 電腦不能顯示中文'
date: 2012-01-10T00:00:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2224
permalink: '/2012/01/cannot-via-chinese-on-computer-%e9%9b%bb%e8%85%a6%e4%b8%8d%e8%83%bd%e9%a1%af%e7%a4%ba%e4%b8%ad%e6%96%87/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
剛剛安裝好電腦 當我想開紿繼續寫網誌時  
卻出現了怪獸文字&#8230;所有中文字都變了方塊&#8230;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/58f648ae4f914438b372c5dc7a696e50" alt="Cannot show chinese in windows 7" width="491" height="312" />  
記得很久之前也遇過差不多的問題&#8230;  
原因是因為這一個原裝的**Windows 7**是**英文版**的  
所以預設的設定是英文..當程式不支援**Unicode**時他的預設文定也會選擇英文

解決方法其實很簡單&#8230;  
在電腦上按一下&#8221;**開始/Start**&#8221; -> &#8220;**Control Panel/控制台**&#8221;  
在&#8221;控制台&#8221; 上選擇 &#8220;**Region and Language**&#8221;  
之後選擇&#8221;**Administrative**&#8221; 分頁  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e4438b96d5fb4ead87177c03673b16ca" alt="Region and Language Administrative tab - Languag for non-unicode programs" width="480" height="555" /> 

大家會看到在 &#8220;**Language for non-Uniode programs**&#8221; 選擇的是 &#8220;**English (United Kingdom)**&#8221; 或是 &#8220;**English (United State)**&#8221; 等的英語國家

大家只需要按一下&#8221;**Change system locale**&#8221;  
之後便會看到 &#8220;**Region and Language Settings**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3c0598e0de3341b78ea72ce32865598b" alt="Region and Language Settings" width="485" height="550" /> 

在&#8221;**Current system locale**&#8221; 的下拉表上選擇 你所使用的語言 E.G.&#8221;**Chines (Traditional, Hong Kong S.A.R.)**&#8221;  
之後按&#8221;**OK**&#8221; 便可以了

之後大家便需要從新開啟電腦 去套用新的設定  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b42c8dad9b934695b99522a6001fbe07" alt="System locale has been changed. You must restart Windows for the changes to take effect." width="479" height="589" /> 

重新啟動之後.. 再次開啟之前的文件便可以看到中文字了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e2d4b45e613a4f4e9de7bf566b58b9bb" alt="display chinese character in notepad has been fixed" width="497" height="330" /> 

Hope you find it useful