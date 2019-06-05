---
id: 2641
title: 'SCRIPT5022: Sys.WebForms.PageRequestManagerServerErrorException: Input string was not in a correct format'
date: 2013-02-16T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2641
permalink: /2013/02/script5022-sys-webforms-pagerequestmanagerservererrorexception-input-string-was-not-in-a-correct-format/
categories:
  - ASP.Net Tips and Tricks
tags:
  - IE10
  - SCRIPT5022
---
今天又有客戶投訴公司的網頁有問題..  
他們不能Download Invoice  
我們試了很多不同的**Browser**終於找到了問題了  
他們下載不到Invoice 的原因是因為我們用了**ASP.Net** 的**Image Button Control**  
而**IE10** 和 以前的**IE** 對這個Control 的方法是不一樣的  
所以便出現了這個問題  
當我們按下這些**Image Button**的時候  
在**IE Developer tool**上的便會出現以下的錯誤  
&#8220;**SCRIPT5022: Sys.WebForms.PageRequestManagerServerErrorException: Input string was not in a correct format**. &#8220; **ScriptResource.axd**  
**解決方法**:  
**方法一**:  
有很多朋友說在**Server** 上安裝 **.Net 4.5** 把**Application Pool**從**.Net 4** 轉成 .Net 4.5便可以了

**方法二**:  
另一個解決方法是在 相關的頁面上的<**Head**> Tag 入

[html]  
<meta http-equiv="X-UA-Compatible" content="IE=9" />  
[/html]

加入以下的**Meta Tag**..當用戶使用**IE10**的話..嘗試便他們的**IE10** 以**IE9** 模式瀏覽網頁  
在我的情況下我在**Master Page**上加入了便解決這個問題的

Hope you find it useful