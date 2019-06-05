---
id: 378
title: '.Net Post XML via HTTPS Notes 1 [Convert XSD to .Net Class]'
date: 2009-08-18T18:18:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/18/net-post-xml-via-https-notes-1-convert-xsd-to-net-class
permalink: /2009/08/net-post-xml-via-https-notes-1-convert-xsd-to-net-class/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6157683202013705530"
categories:
  - .Net Tips And Tricks
  - Web Services
  - XML
---
最近公司有一個project是要用另外一間公司的 XML Interface 既Webservice 去做exchange data.  
其實只要這間公司提供WSDL 既Address 給我們  
這個project 便很容易完成&#8230;  
很可惜這間公司不願提供WDSL file  
所以最後便要自己學怎樣在VB.Net 入面post XML 去HTTP 了

便這了這篇筆記了

還記得之前用WSDL時  
當我Add 了Service Reference Visual Studio 便會自動產生了和這 Web service 有關的 .NET Object 和Connection End Point  
一切都十分方便&#8230;

現在所有事都要自己Handle　感到有點煩惱&#8230;  
等一個STEP 便是要找 方法把  
Developer Guide 入面的XSD 轉做 .Net Object  
或者你要自己寫一些CLASSES 出來  
去做一些 function 可以return 到XML OUTPUT 可以Match 到  
Developer Guide 入面你需要POST的 XML Rule.

以下是我的做法

首先你要找到這個<span style="font-weight:bold;">XSD.EXE</span> file  
在我的電腦入面是在以下的directory  
<span style="color:rgb(51,51,255);">C:Program FilesMicrosoft SDKsWindowsv6.0ABin</span>

或者你可以試試 SEARCH  
&#8220;<span style="font-weight:bold;">xsd.exe</span>&#8221; 之後copy 這個檔案去另一個location  
或到&#8221;<span style="font-weight:bold;">xsd.exe</span>&#8220;後便用Command Prompt  
[我將這個.EXE copy 到 裝有 xsd 檔案的 directory 入面 (這樣可以方便自己打小一些path)]

之後開啓command prompt  
&#8220;<span style="font-weight:bold;">Start</span>&#8220;-> &#8220;<span style="font-weight:bold;">Run</span>&#8220;-> Type &#8220;<span style="font-weight:bold;">cmd</span>&#8221; ->Press &#8220;<span style="font-weight:bold;">Enter</span>&#8220;  
在command prompt 入面  
進入有 &#8220;<span style="font-weight:bold;">xsd.exe</span>&#8221; 的 directory 入面  
之後打以下的Command 你便可以create 一個 class base on 這個xsd 檔案了  
MyXMLObjNameSpace 是我想這個Class 用的namespace.  
XMLToExampleCLass.xsd 是我轉的xsd file.  
我用的 language 是 VB.NET

VB  
<span style="color:rgb(0,153,0);font-size:85%;"><span style="font-weight:bold;">xsd.exe &#8211;<span style="font-style:italic;">c</span> &#8211;<span style="font-style:italic;">l:vb</span> &#8211;<span style="font-style:italic;">n:</span>MyXMLObjNameSpace XMLToExampleCLass.xsd</span></span>

C#  
<span style="color:rgb(0,153,0);font-size:85%;"><span style="font-weight:bold;">xsd.exe <span style="font-style:italic;">-c -l:c# -n:</span>MyXMLObjNameSpace XMLToExampleCLass.xsd</span></span>

<span style="color:rgb(0,153,0);font-size:85%;"><span style="font-weight:bold;">xsd.exe <span style="font-style:italic;">-c</span>[-c mean general Class] <span style="font-style:italic;">-l:</span>[Language Name e.g. c#/vb] <span style="font-style:italic;">-n:</span>[Namespace] [XSD file name]</span></span>

如果你的XSD 檔案不是 proper define command prompt 便會出示一些error message 說出那裡出現問題就好像下面一樣  
[<img src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/4a289c78d50e41b3ab9aa6360145924e" alt="" border="0" />](http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/4a289c78d50e41b3ab9aa6360145924e)  
這樣你便要看清楚你的XSD 檔案是否Well define 了

如果你的xsd 檔案是沒有問題  
他便會出現&#8230;  
<span style="font-size:85%;"><span style="font-style:italic;"><span style="font-weight:bold;">Writing file</span> &#8220;C:pathXMLToExampleCLass.vb&#8221;</span></span>

當你完成之後只要COPY 這個VB 檔案到你的VB project  
之後imports 這個namespace 你便可以使用這個class 了

E.G.  
VB  
<span style="color:rgb(0,153,0);font-size:85%;"><span style="font-style:italic;font-weight:bold;">Imports MyProgram.MyXMLObjNameSpace</span> </span>  
C#  
<span style="font-size:85%;"><span style="font-weight:bold;font-style:italic;color:rgb(0,153,0);">using MyProgram.MyXMLObjNameSpace;</span></span>

Hope you find it useful.  
如果你有更好的方法, 歡迎大家一齊來研究研究