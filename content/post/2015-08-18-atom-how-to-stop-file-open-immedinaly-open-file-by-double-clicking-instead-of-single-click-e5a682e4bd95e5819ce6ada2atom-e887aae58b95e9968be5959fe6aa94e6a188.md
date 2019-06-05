---
id: 3481
title: 'Atom How to stop file open immedinaly /open file by double clicking instead of single click  &#8211; 如何停止Atom 自動開啟檔案'
date: 2015-08-18T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3481
permalink: '/2015/08/atom-how-to-stop-file-open-immedinaly-open-file-by-double-clicking-instead-of-single-click-%e5%a6%82%e4%bd%95%e5%81%9c%e6%ad%a2atom-%e8%87%aa%e5%8b%95%e9%96%8b%e5%95%9f%e6%aa%94%e6%a1%88/'
categories:
  - Atom
tags:
  - Atom
  - Atom Plugins
  - GitHub
---
最近朋友介紹我一個由**GitHub** 出的 **Open Source Text Editor 名字叫 &#8220;<a href="https://atom.io/" target="_blank">Atom</a>&#8220;**  
他說很好用的  
下載之後感覺他和<a href="http://www.sublimetext.com/2" target="_blank"><strong>SublimeText</strong> </a>很似..  
使用感覺良好.都是沒有一個Proj**e**ct的概念..  
主要都是一個**Text Editor**..但是有一個**Folder Structure**的 pane

有了一會發現了有一個使用習慣的問題..  
就是他和**SublimeText** 一樣..  
當你按一檔案名時..他便會開啟了那個檔案..  
令到**Editor** 上開啟了很多**File Tab**..  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/319/19632089064_393bb273f4_z.jpg?resize=625%2C384" alt="Atom Auto Open Tab Issue" width="625" height="384" data-recalc-dims="1" />  
有時候會感到有點混亂

做了一會Research 之後終於找到解決方法了

**解決方法**十分簡單

首先按右上角&#8221;**File**&#8221; ->&#8221;**Settings**&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/477/19633775063_f00fe854e7_z.jpg?resize=500%2C292" alt="Atom -> File -> Settings" width="500" height="292" data-recalc-dims="1" /> 

之後在**Atom Settings Tab** 上按一下&#8221;**Packages**&#8221;  
在**Installed Packages** 下面的 **TextBox** 輸入 &#8220;**Tabs**&#8221; 便會找到Tabs 這個**Package**..之後按&#8221;**Settings**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/483/20066714630_2aec2b9f90_z.jpg?resize=625%2C299" alt="Atom Settings -> Packages -> Search for Tabs Packages" width="625" height="299" data-recalc-dims="1" /> 

在**Tabs packages** 的**Settings** 內 選擇 &#8220;**Use preview tab**&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/354/19633775303_d9f38417ae_z.jpg?resize=625%2C528" alt="Atom Tabs - Use Preview Tabs" width="625" height="528" data-recalc-dims="1" />  
當你Tick了&#8221;**Use preview tab**&#8220;.. **Atom** 便只會 **Preview** 預覽 你按下的檔案..  
當你作出 修改時..他們才會正式開啟

Hope you find it useful