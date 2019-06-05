---
id: 1779
title: '.Net &#8211; Auto-Implemented Properties'
date: 2011-05-01T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1779
permalink: /2011/05/net-auto-implemented-properties/
categories:
  - .Net Tips And Tricks
---
不知什麼時候開始喜歡用**C#** 來寫程式..  
可能是因為公司多了同事用**C#**..  
為了方便大家.所以用**C#**比較合適一點

但是我仍然要使用**VB.Net** 來  
維護之前所寫的程式..  
所以有時知道一些寫C# 寫Code的 **Syntax** 但是不知道VB 是如何寫的  
今天想和大家介紹一下一個叫做 **Auto-Implemented Properties** 的東西..  
在.Net 3.0 時已經有的..  
就是以前如果在**Class** 上寫一個**Property**屬性 時 需要寫一個 **Private** 的 **property**  
之後要寫一個**Public 的method 來read/write 資料到這個property** 上的  
E.G

**C#**  
[csharp]  
private string _ShareChiWai

public String ShareChiWai  
{  
get { return _ShareChiWai; }  
set{_ShareChiWai = value;}  
}  
[/csharp]  
VB.Net  
[vb]  
Private _ShareChiWai as String  
Public Property ShareChiWai As String  
Get  
Return _ShareChiWai  
End Get  
Set(ByVal value As Stringl)  
_ShareChiWai = value  
End Set  
End Property  
[/vb]  
在**.Net 3.0** 之後的**C#** 和**.Net 4 的 VB.Net**  
加入了這個叫做 **Auto-Implemented Properties 的Feature.**. 令到大家的Code更簡潔..寫程式時更方便..

**C#**  
[csharp]  
public String ShareChiWai {get;set;}  
[/csharp]  
**VB.Net**  
[vb]  
Public Property ShareChiWai As String  
[/vb]  
使多有關**Auto-Implemented Properties** 的詳情可以參考以下URL

**C# Auto-Implemented Properties**  
 <a title="C# Auto-implemented Properties" href="http://msdn.microsoft.com/zh-cn/library/bb384054.aspx" target="_blank">http://msdn.microsoft.com/zh-cn/library/bb384054.aspx</a>

**VB Auto-Implemented Properties**  
 <a title="VB.Net Auto-Implemented Properties" href="http://msdn.microsoft.com/zh-cn/library/dd293589.aspx" target="_blank">http://msdn.microsoft.com/zh-cn/library/dd293589.aspx</a>

Hope you find it useful