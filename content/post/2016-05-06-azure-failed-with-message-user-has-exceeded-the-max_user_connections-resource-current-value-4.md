---
id: 3652
title: 'Azure failed with message: User has exceeded the &#8216;max_user_connections&#8217; resource (current value: 4)'
date: 2016-05-06T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3652
permalink: /2016/05/azure-failed-with-message-user-has-exceeded-the-max_user_connections-resource-current-value-4/
categories:
  - Windows Azure
tags:
  - Azure
  - Microsoft Azure
  - mysql
  - Windows Azure
---
最近和朋友做一個 **ASP.Net MVC** 的 **Freelance Project**  
因為生活習慣不同..所以我們都是不同時間寫Code的  
但是一起用同一個 **Azure Free** Tier的 **MySQL Server**  
沒有很大的問題  
但是當我們嘗試Merge我們的Project 做 Testing時候便出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>User has exceeded the &#8216;max_user_connections&#8217; resource (current value: 4)</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7196/26753640252_5eb9a476f7_z.jpg?resize=625%2C115" alt="Azure has exceeded the 'max_user_connections' resource (current value: 4)" width="625" height="115" data-recalc-dims="1" />  
原來 **Free Tier的 MySQL 是限制了 可以Connect到這個MySQL Database**的 可以有**4個 Connection**  
所以最後還是開始學習使用**Docker** 做我們的Development Database

當做Demo時才使用Azure 的**Free Tier MySQL**