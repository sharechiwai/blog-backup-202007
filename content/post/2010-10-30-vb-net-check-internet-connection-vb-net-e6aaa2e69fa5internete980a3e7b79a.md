---
id: 838
title: 'VB.net Check Internet Connection &#8212; VB.NET 檢查Internet連線'
date: 2010-10-30T00:00:29+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=838
permalink: '/2010/10/vb-net-check-internet-connection-vb-net-%e6%aa%a2%e6%9f%a5internet%e9%80%a3%e7%b7%9a/'
categories:
  - .Net Tips And Tricks
---
<div id="_mcePaste">
  今天終於決定了重寫一個自己在2-3年前寫的一個程式 [在公司&#8230;回看這時的Code自己的技術真係很差]
</div>

<div id="_mcePaste">
  這個程式其實可以把他寫成一個<strong>Service</strong>
</div>

<div id="_mcePaste">
  他的職責是處理一些我們的客戶在網站上Request的資料
</div>

<div id="_mcePaste">
  第一個功能是 寫一個功能來檢查公司的網路Internet有沒有連上
</div>

<div id="_mcePaste">
  因為這個程式大部份的時間都會使用其他公司提供的Web Service/ Web Interface
</div>

<div id="_mcePaste">
  來Request 資料的
</div>

<div id="_mcePaste">
  如果Internet 有問題時
</div>

<div id="_mcePaste">
  這些Web Service 便不能使用&#8230;
</div>

<div id="_mcePaste">
  有機會令到這個程式Lock 住在這個Stage中
</div>

<div id="_mcePaste">
  所以便要寫一個檢查電腦和這個Web <strong>Service </strong>的連線有沒有問題 才繼續執行
</div>

<div id="_mcePaste">
  原來用來檢查Internet 有沒有Connected 的程式碼是很簡單的
</div>

<div id="_mcePaste">
  我寫了一個功能 叫 <strong>IsConnectedToInternet</strong>, 你可以Pass 一個URL 給他去檢查
</div>

<div id="_mcePaste">
  看看你的電腦能不能連線到這個URL, 如果你沒有傳入這個Parameter的話
</div>

<div id="_mcePaste">
  他便會使用 這個URL: <a href="http://www.yahoo.com">http://www.yahoo.com</a>
</div>

[vb]  
Public Function IsConnectedToInternet(Optional ByVal URLToCheck As String = "http://www.yahoo.com") As Boolean  
&#8216;建立一個WebRequest 到我們所設定的網址  
Dim req As System.Net.WebRequest = System.Net.WebRequest.Create(URLToCheck)  
WebResponse 是用來收集當我們發完一個Web Request 後所回傳回來的Response  
Dim resp As System.Net.WebResponse  
Try  
&#8216;看看能不能收集到 資料  
resp = req.GetResponse()  
&#8216;成功後關閉Response  
resp.Close()  
&#8216;把Response 設定成Nothing 方法release resource  
resp = Nothing  
&#8216;把Resquest 設定成Nothing 方法release resource  
req = Nothing  
Return True  
Catch ex As Exception  
&#8216;當有錯誤發生時, 這証明了..我們不能成功和這個URL 建立連線  
&#8216;把Resquest 設定成Nothing 方法release resource  
req = Nothing  
Return False  
End Try  
End Function  
[/vb]

<div id="_mcePaste">
  Hope you find it useful
</div>