---
id: 562
title: '.Net Remove Empty Row on DataGridView &#8212; .Net 去除DataGridView 上的空白行'
date: 2010-09-06T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=562
permalink: '/2010/09/net-remove-empty-row-on-datagridview-net-%e5%8e%bb%e9%99%a4datagridview-%e4%b8%8a%e7%9a%84%e7%a9%ba%e7%99%bd%e8%a1%8c/'
jabber_published:
  - "1283702968"
email_notification:
  - "1283702969"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982586";}";'
categories:
  - .Net Tips And Tricks
---
有用開**DataGridView** 的朋友都會發現  
當你從資料庫取得了一些資料  
之後把他們放在**DataGridView** 上  
總會有一行空白的行在這個**DataGridView** 的最底部

如果你只希望顯示資料, 在**DataGridView** 上有一行空白的行  
感覺會有點怪怪的  
其實這個空白行主要用來方便使用者的  
當他們的**DataGridView** 是雙向的話, 使用者可以運用  
這一個空白行加入新資料

但當你用到  
**DataGridView.RowCount** 的話即使是沒有資料, 他也會 **Return 1**的  
因為有一行空白行&#8230;這可能有一點 Confusing..

如果大家想除去這空白行 可以在**DataGridView** 的 屬性上設定  
把**AllowUserToAddRows** 屬性設定成 **False** 便可  
[<img class="alignnone size-full wp-image-563" title="AllowUserToAddRows" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8d30a6450a684cacb5826fc6e2358193/renditions/fullsize.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8d30a6450a684cacb5826fc6e2358193/renditions/fullsize.jpg)

Hope you find it useful