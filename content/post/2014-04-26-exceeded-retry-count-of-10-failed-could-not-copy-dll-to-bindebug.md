---
id: 3155
title: 'Exceeded retry count of 10. Failed &#8211; Could not copy dll to bin\debug'
date: 2014-04-26T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3155
permalink: /2014/04/exceeded-retry-count-of-10-failed-could-not-copy-dll-to-bindebug/
categories:
  - .Net Tips And Tricks
tags:
  - .Net Troubleshooting
---
最近在開發的一個WinForm的程式時常常出現以下的錯誤信息  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7378/14197983394_8798d62a34_z.jpg?resize=548%2C96" alt="Could not Copy. Exceeded retry count of 10. Failed." width="548" height="96" data-recalc-dims="1" />  
&#8216;**<span style="color: #ff0000;">Could not copy d:\tfsservice\sharechiwai\bin\debug\sharechiwai.dll&#8217; to &#8220;bin\Debug\sharechiwai.dll&#8221;. Exceeded retry count of 10. Failed.</span>**&#8216;

**解決方法**:  
大家可以到 工具欄上 按&#8221;**Build**&#8221; -> &#8220;**Clean Solution**&#8221;  
之後再按 &#8220;**Build**&#8221; -> &#8220;**Rebuild Solution**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7358/14218202833_061071529d_z.jpg?resize=388%2C150" alt="Build -> Clean Solution" width="388" height="150" data-recalc-dims="1" /> 

之後應該可以**Debug** 這個Project的

Hope you find it useful