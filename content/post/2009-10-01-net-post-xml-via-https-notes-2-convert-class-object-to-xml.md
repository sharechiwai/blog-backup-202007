---
id: 354
title: '.Net Post XML via HTTPS Notes 2 [Convert Class object to XML]'
date: 2009-10-01T10:01:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/10/01/net-post-xml-via-https-notes-2-convert-class-object-to-xml
permalink: /2009/10/net-post-xml-via-https-notes-2-convert-class-object-to-xml/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "217912079001758346"
categories:
  - .Net Tips And Tricks
  - XML
---
上一篇筆記示範了怎麼把XSD 轉成.NET CLASSES  
[ .Net Post XML via HTTPS Notes 1 [Convert XSD to .Net Class]](http://sharechiwai.blogspot.com/2009/08/net-post-xml-via-https-notes-1-convert.html)  
今日我們便可以利用上次Generate 出來的 classes  
來建立一些我們需要用到的Object 了  
最重要既一個步驟是 要在 Class 上 加入之前create 的 namespace.

當大家建立好要用的object 時  
我們便可以開始了

首先我們要加入一些Reference  
<span style="color:#339999;">Imports System.Xml.Serialization</span><span style="color:#339999;"> </span>  
<span style="color:#339999;">Imports System.IO</span> <span style="color:#339999;">Imports System.Text</span>

我們要建立一個 XmlSerializer Object 要輸入的parameter 是你將要Convert 的 Object Type  
E.G<span style="color:#6aa84f;">. &#8216;我要convert 的Class 是</span>  
Dim ClassToBeConvert as New **ClassNameOfTheObj**  
&#8216;&#8212;- <span style="color:#6aa84f;">當你改好這個Class 入面的 Properties 後 我們便可以轉這個Class 做XML String 了</span>  
Dim ConvertToXmlString As New StringBuilder <span style="color:#6aa84f;">&#8216;這個用來 Store這個XML String 的</span>

Dim xSerializer as New XmlSerializer(GetType(**ClassNameOfTheObj**))  
Dim sw as New StringWriter(CovertToXMLString)  
xSerializer.Serialize(sw, ClassToBeConvert )  
sw.Close()

<span style="font-size:x-small;">MsgBox(ConvertToXmlString .ToString)</span><span style="color:#6aa84f;"><span style="font-size:x-small;"> </span>&#8216;這便會POPUP 這個轉CLASS 的XML STRING 了</span>

由於這個XML Interface 要我 post XML String 到這個HTTPS  
所以如果我直接把剛剛 convert 好的 XML String post 去HTTPS  
會有Exception 出現的  
因為這個剛剛Convert 出來的XML 是一個Well Form的 XML  
<span style="color:#6aa84f;">[這個XML String 會 contain string 的 format 所以便會有space 和 隔行]</span>  
所以會有自動隔行 [vbCrLf] 的情況出現&#8230;  
<span style="color:red;font-size:85%;font-weight:bold;">&#8220;Specified value has invalid CRLF characters. Parameter name: value&#8221;</span>

解決的方法亦都是很簡單  
只要使用 String.Replace這個function便可  
E.G.**<span style="font-size:x-small;">MsgBox(ConvertToXmlString .ToString.Replace(vbCrLf, &#8220;&#8221;))</span>** &#8216;這便會POPUP 這個轉CLASS 的XML STRING 了  
這樣我們便有了一個可以在HTTPS 上Post 的 XML String了

待續&#8230;  
Hope you find it useful.  
如果你有更好的方法, 歡迎大家一齊來研究研究