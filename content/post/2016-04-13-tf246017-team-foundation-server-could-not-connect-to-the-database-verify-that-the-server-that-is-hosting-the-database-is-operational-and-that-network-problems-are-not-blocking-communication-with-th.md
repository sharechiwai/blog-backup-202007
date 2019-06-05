---
id: 3617
title: 'TF246017: Team Foundation Server could not connect to the database. Verify that the server that is hosting the database is operational, and that network problems are not blocking communication with the server.'
date: 2016-04-13T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3617
permalink: /2016/04/tf246017-team-foundation-server-could-not-connect-to-the-database-verify-that-the-server-that-is-hosting-the-database-is-operational-and-that-network-problems-are-not-blocking-communication-with-th/
categories:
  - Team Foundation Server
tags:
  - SQL Server
  - TFS
  - TFS Server
---
今日公司的同事不能連接公司的 **TFS Server.**

當嘗試連接時 出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>TF246017: Team Foundation Server could not connect to the database. Verify that the server that is hosting the database is operational, and that network problems are not blocking communication with the server.</strong></span>&#8221;

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1635/25763372664_7b78c8668d_z.jpg?resize=432%2C96" alt="TF246017" width="432" height="96" data-recalc-dims="1" /> 

**解決方法**  
重新啟動 這個**TFS Server**的 **Database Server**的 **SQL Service**便可以了

Hope you find it useful