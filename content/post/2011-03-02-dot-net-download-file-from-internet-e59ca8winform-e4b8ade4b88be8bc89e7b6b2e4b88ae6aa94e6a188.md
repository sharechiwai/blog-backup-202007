---
id: 949
title: '.Net Download File from Internet &#8212; 在.Net 中下載網上檔案'
date: 2011-03-02T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=949
permalink: '/2011/03/dot-net-download-file-from-internet-%e5%9c%a8winform-%e4%b8%ad%e4%b8%8b%e8%bc%89%e7%b6%b2%e4%b8%8a%e6%aa%94%e6%a1%88/'
categories:
  - .Net Tips And Tricks
---
最近需要寫一個小程式 跟據資料庫的數據去下載一些網上的資料..  
以便其他應用程式使用&#8230;

方法十分簡單..  
我會使用WebClient 這個Object  
以下是一些Sample Code

VB.Net

[vb]  
&#8216;先建立一個 WebClient的Object  
Dim wc As New WebClient()

&#8216;之後使用DownloadFile Method 來 Download 檔案  
&#8216;wc.DownloadFile("下載檔案的網扯", "檔案下載到本機的位置和檔案名稱")  
wc.DownloadFile("http://sharechiwai.com/static/i/logo.png", "d:\sharechiwailogo.png")

&#8216;最後 使用Dispose method來清理資源  
wc.Dispose()  
[/vb]

c#

[csharp]  
&#8216;先建立一個 WebClient的Object  
WebClient wc = new WebClient();

&#8216;之後使用DownloadFile Method 來 Download 檔案  
&#8216;wc.DownloadFile("下載檔案的網扯", "檔案下載到本機的位置和檔案名稱")  
wc.DownloadFile("http://sharechiwai.com/static/i/logo.png", @"d:\sharechiwailogo.png");

wc.Dispose()  
wc.Dispose();  
[/csharp]

Hope you find it useful