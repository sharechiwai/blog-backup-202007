---
id: 2132
title: '免費 的 online Version Control System &#8211; 使用BitBucket 的服務來備份你的程式碼'
date: 2011-11-06T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2132
permalink: '/2011/11/%e5%85%8d%e8%b2%bb-%e7%9a%84-online-version-control-system-%e4%bd%bf%e7%94%a8bitbucket-%e7%9a%84%e6%9c%8d%e5%8b%99%e4%be%86%e5%82%99%e4%bb%bd%e4%bd%a0%e7%9a%84%e7%a8%8b%e5%bc%8f%e7%a2%bc/'
categories:
  - Experience Share / 經驗分享
tags:
  - BitBucket
  - Git
  - Source Control
---
經一事長一智..經過之前失去所有電腦上的數據.包括, 相片,程式碼 和功課的慘痛經驗之後..  
係時候要留意一下 一些**雲端的backup solution** [網上的方案]

今天想和大家介紹的是在**BitBucket** 使用**Git**  
其實**BitBucket**和**GitHub**是差不多的  
大家都是可以用到做**source control**的  
是**分散式版本控制系統** &#8211; **Distributed Version Control Systems**

**什麼是分散式版本控制系統**  
以我的理解是一個在每一台電腦上的程式碼都可以有自己的一個**repositories**..  
大家可以隨身把寫好的程式碼**commit**到自己的**Repositories** 上.  
或從**Repositories**上**Roll Back**/**Restore**之前寫好的程式碼..  
把自己搞亂了的程式碼還原..  
由於在很多請況下都會有多過一個**Developer**在同一個Project 上開發不同的Modules  
所以分散式版本控制系統 會有一個**Central Repository** 用來把寫好的程式碼集結在一起

當程式碼有些重疊時&#8230;  
便會有一個功能給大家**merge** 重疊/或系統不能分別那一個是要用的版本的程式碼用人手**Merge**成一個較好的版本..  
其他的Developer可以 連接到這個Central Repository上取最新的版本..  
所以用起來比較方便和有效率

**BitBucket** 和**GitHub**最大分別是  
GitHub 的免費Account 暫時 是只提供無限的公開的repositories[庫]和庫內可以有無限的參與者和他只支援Git 沒有支援其他的source control  
&#8220;**Unlimited public repositories and unlimited public collaborators**&#8221;

BitBucket的免費account 就 有無限的公開和私人的repositories[庫] 但是只可以有最多5個的參與者/使用者  
&#8220;**5 users free plan and you can have unlimited public and private repositories.**&#8221;  
而BitBucket 有提供 Git 和 Mercurial 的 分散式版本控制的 服務

詳情可以自己參考他們的官方網頁  
**BitBucket**  
 <a title="BitBucket" href="https://bitbucket.org/" target="_blank">https://bitbucket.org/</a>

**GitHub**  
 <a title="GitHub" href="https://github.com/" target="_blank">https://github.com/</a>

將來我會寫一個如何在 電腦上安裝 **Git** 和設定**BitBucket** 的貼士 有興趣的朋友可以留意給我一些意見

<div>
  有興趣在Windows 的電腦上安裝 Git 和設定BitBucket 的朋友可以參考以下我的網誌<br /> <a title="Setup Git for BitBucket on Windows – 在Windows 上設定Git" href="http://blog.sharechiwai.com/2011/11/setup-git-for-bitbucket-on-windows-%e5%9c%a8windows-%e4%b8%8a%e8%a8%ad%e5%ae%9agit/" target="_blank">Setup Git for BitBucket on Windows &#8211; 在Windows 上設定Git</a>
</div>

Hope you find it useful