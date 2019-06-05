---
id: 2126
title: '.Net Convert Durarion from Seconds to HH:MM:SS &#8211; .Net 把秒 轉成 時間 HH:MM:SS'
date: 2011-10-05T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2126
permalink: '/2011/10/net-convert-durarion-from-seconds-to-hhmmss-net-%e6%8a%8a%e7%a7%92-%e8%bd%89%e6%88%90-%e6%99%82%e9%96%93-hhmmss/'
categories:
  - .Net Tips And Tricks
---
今天在我的**ASP.Net MVC** 網頁上發現忘記了加入一個把秒數轉為 時間: **HH:MM:SS**的功能

之後便嘗試寫一個方法去解決這個問題..  
最後..因為自己的概念不好的關係..  
最後用了很多時間才完成..  
所以.. 還是把這個功能放進Blog 上  
方便自己將來再有需要使用這個功能時可以 用來參考

**解決方法**:  
**C#**

[csharp]  
public static string ConvertDurationToHHMMSS(long duration)  
{  
//轉換成秒  
int SS = (int) duration % 60;  
//轉換成分鐘  
int MM = (int) (duration / 60) % 60;  
//轉換成時間  
long HH = (long)(duration / 60 / 60);  
//使用String Format 令到他們 會有 "0"/"00" 為開始  
return String.Format("{0:#00}:{1:#00}:{2:#00}", HH, MM, SS);

}  
[/csharp]

**VB**

[vb]  
Public Shared Function ConvertDurationToHHMMSS(ByVal duration As Long) As String  
&#8216;轉換成秒  
Dim SS As Integer = duration Mod 60  
&#8216;轉換成分鐘  
Dim MM As Integer = (duration \ 60) Mod 60  
&#8216;轉換成時間  
Dim HH As Long = duration \ 60 \ 60  
&#8216;使用String Format 令到他們 會有 "0"/"00" 為開始  
Return String.Format("{0:#00}:{1:#00}:{2:#00}", HH, MM, SS)  
End Function  
[/vb]

Hope you find it useful