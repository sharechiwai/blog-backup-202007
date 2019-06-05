---
id: 3712
title: '小小Vagrant/ Linux 筆記 &#8211; Ubuntu Unattended Upgrade'
date: 2016-07-06T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3712
permalink: '/2016/07/%e5%b0%8f%e5%b0%8fvagrant-linux-%e7%ad%86%e8%a8%98-ubuntu-unattended-upgrade/'
categories:
  - Vagrant 筆記
tags:
  - Ubuntu
  - Vagrant
---
**小小筆記**  
最近又繼續玩**Vagrant**  
不知道為什麼嘗試用Official 的**Vagrant Ubuntu** 16.04 Image時常常出現問題..  
不能**SSH** 到這個**Vagrant Box**  
所以便想在**Provision** 時更新這個系統了

那麼如何可以令**Linux** 可以**Unattended地更新**呢  
**解決方法**  
我們可以執行以下指令

<pre>sudo do-release-upgrade -f DistUpgradeViewNonInteractive
</pre>

Hope you find it useful