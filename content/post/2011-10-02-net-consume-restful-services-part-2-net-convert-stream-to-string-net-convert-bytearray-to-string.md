---
id: 2122
title: .Net Consume RESTFUL Services Part 2 .Net Convert Stream to String/ .Net Convert ByteArray to String
date: 2011-10-02T00:00:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2122
permalink: /2011/10/net-consume-restful-services-part-2-net-convert-stream-to-string-net-convert-bytearray-to-string/
categories:
  - .Net Tips And Tricks
tags:
  - JSON
  - Restful Services
  - WebClient
---
為了方便測試在**RESTFUL Call** 的Return的結果  
所以我想看看有沒有方法把這個**Response Stream轉換成String**

完來解決方法十分簡單&#8230;  
只是使用**StreamReader** 使用 **ReadToEnd** 的方法 (**ReadLine**,**ReadBlock**和**Read** 也可以的**. ReadToEnd**比較方便)把 Stream讀取出來便可以了  
**  
解決方法**  
我用了上一次的Sample在這裡做了個示範

有興趣的朋友可以按以下連結看看  
 <a title=".Net Consume RESTFUL Services – Make Restful Services Call and Handle JSON reponse" href="http://blog.sharechiwai.com/2011/09/net-make-restful-services-call-and-handle-json-reponse/" target="_blank">.Net Consume RESTFUL Services – Make Restful Services Call and Handle JSON reponse</a>

在這裡我只更新**OpenReadCompletedEventHandler** 這個**Section** 示範這個結果

[csharp]  
void wc_OpenReadCompleted(object sender, OpenReadCompletedEventArgs e)  
{  
if (e.Error == null)  
{  
//建立新的StreamReader把 WebClient OpenReadCompleted的Stream Assign 到Stream Reader上  
StreamReader reader = new StreamReader(e.Result);  
//使用StreamReader的ReadToEnd 來讀取在這個Stream上的內容  
string result = reader.ReadToEnd();  
//用MessageBox.Show 來顯示結果  
MessageBox.Show(result);  
}  
}  
[/csharp]

Hope you find it useful