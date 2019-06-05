---
id: 3800
title: 'Batch File start in specific directory &#8211; 如何建立一個Batch檔案去在指定路徑開啟 Command Prompt'
date: 2017-01-16T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3800
permalink: '/2017/01/batch-file-start-in-specific-directory-%e5%a6%82%e4%bd%95%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8bbatch%e6%aa%94%e6%a1%88%e5%8e%bb%e5%9c%a8%e6%8c%87%e5%ae%9a%e8%b7%af%e5%be%91%e9%96%8b%e5%95%9f-command-p/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Symfony
---
最近朋友介紹我開始使用**Symfony**  
之後便開始嘗試使用**symfony** 來開發..

在**symfony**很多時候都會使用到**command prompt**..  
其實現在開發web application 都會常常使用 npm / bower 等等的 CLI

**那麼怎樣可以建立一個Batch檔案去在指定路徑開啟 Command Prompt**

**解決方法**十分簡單  
我們可以建立一個 **.bat** 檔案.. 之後建立一個變數 e.g. Pathname  
之後使用 &#8220;**cd /d**&#8221; **/d** 是**directory** 的意思  
之後加上&#8221;**cmd.exe**&#8220;便可以了 (執行command prompt)

<pre>set Pathname="c:\xampp\htdocs\sharechiwai"
cd /d %Pathname%
cmd.exe
</pre>

hope you find it useful