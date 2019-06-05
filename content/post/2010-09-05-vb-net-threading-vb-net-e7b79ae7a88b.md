---
id: 585
title: 'VB.Net Threading &#8212;VB.Net 線程'
date: 2010-09-05T05:00:55+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=585
permalink: '/2010/09/vb-net-threading-vb-net-%e7%b7%9a%e7%a8%8b/'
jabber_published:
  - "1283637417"
email_notification:
  - "1283637419"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982585";}";'
categories:
  - .Net Tips And Tricks
---
在之前的網誌中, 說了怎樣使用**BackgroundWorker**,  
今次想和大家介紹怎樣使用**Threading** 線程  
有時候我們可以利用**Threading** 和執行一些需時/較複雜的程序  
這樣便可以好像使用**BackGroundWorker**一樣  
避免**WinForm** 出現假死/沒有回應的情況了

這次我也是建立了一個模擬一些需時/較複雜的程序

[vb]  
Public Sub LongProcess() &#8216;用來模擬一些Long Process的Code  
Dim info As Integer = 0  
For i As Integer = 0 To 999999  
For j As Integer = 0 To 9999  
info = i + j  
Next  
Next  
btn_LongProcess.Text = Now.ToLongTimeString&#8217;完成時候 Update 這個Button 的文字為 現在的時間  
MsgBox("Process Completed")

End Sub  
[/vb]  
之後我們可以建立一個Thread來處理這個 程序  
使用方法十公簡單  
[vb]  
&#8216;建立一個新的Thread線程, 設定他將會執行的功能名稱  
Dim MyThreading As New System.Threading.Thread(AddressOf Me.LongProcess)  
&#8216;用.Start來 啟動這個線程Thread</span>  
MyThreading .Start()  
[/vb]  
Hope you find it useful