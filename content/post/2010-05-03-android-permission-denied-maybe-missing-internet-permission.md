---
id: 161
title: 'Android: Permission denied (maybe missing INTERNET permission)'
date: 2010-05-03T23:59:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/03/android-permission-denied-maybe-missing-internet-permission
permalink: /2010/05/android-permission-denied-maybe-missing-internet-permission/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7168956225621339214"
categories:
  - Android
---
今日我又開始繼續寫我的Android Application 了&#8230;由於工作太忙的關係所以很多東西已經忘了&#8230;  
當我在測試我的Application 時&#8230;出現了這個Error message:  
&#8220;**<span style="color:red;">Permission denied (maybe missing INTERNET permission)</span>**&#8220;

只要在 **AndroidManifest.xml** 中的 

下一行加入 了使用**INTERNET** 的 Setting 你便可以在這個Application 連接 Internet了

****

Happy Programming