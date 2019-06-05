---
id: 3250
title: 'Basic stuff need to install on Linux &#8211; 一些安裝Linux 後的基本程式'
date: 2014-06-23T00:00:31+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3250
permalink: '/2014/06/basic-stuff-need-to-install-on-linux-%e4%b8%80%e4%ba%9b%e5%ae%89%e8%a3%9dlinux-%e5%be%8c%e7%9a%84%e5%9f%ba%e6%9c%ac%e7%a8%8b%e5%bc%8f/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Ubuntu
---
我的**Microsoft Azure** 是用**Linux Ubuntu 14.04**版本的  
由于我是新手的關係..所以很多時候嘗試安裝程式是都出現問題..

發現原來有很多東西是要自己預先安裝才可以用的..  
以下是一些基本程式&#8230; 你今天不安裝..相信很快也需要安裝喔.

首先 要更新一下repository

<pre>sudo apt-get update
</pre>

**Git**  
安裝方法 &#8211; 執行以下指令

<pre>apt-get install git
</pre>

**Make**  
之前嘗試使用Make 來 Build 一些東西時出現下的錯誤信息  
&#8220;The program &#8216;make&#8217; is currently not installed. To run &#8216;make&#8217; please ask your administrator to install the package &#8216;make'&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5589/14793775245_e5e15c1bc0_z.jpg?resize=625%2C57" alt="The program 'make' is currently not installed. To run 'make' please ask your administrator to install the package 'make'" width="625" height="57" data-recalc-dims="1" />  
安裝 Make 十分簡單

<pre>apt-get install make
</pre>

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3889/14607069730_ebb24e9fbc_z.jpg?resize=537%2C166" alt="Linux Install Make" width="537" height="166" data-recalc-dims="1" /> 

將來會不定時更新 以和大家分享 / 安裝有用的**Linux** 程式

Hope you find it useful