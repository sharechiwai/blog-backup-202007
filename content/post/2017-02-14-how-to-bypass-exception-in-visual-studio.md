---
id: 3817
title: How to bypass Exception in Visual Studio
date: 2017-02-14T09:18:43+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3817
permalink: /2017/02/how-to-bypass-exception-in-visual-studio/
categories:
  - .Net Tips And Tricks
tags:
  - exception
  - visual studio
  - Visual Studio 2015
---
最近係公司寫的一個Web app 因為backend 的web api 有些問題的關係。。所以不能連接要development server 上某些data 所以久不久便彈一些 unhanded exception出來。。

嘗試 Debug的時間。。因為Visual Studio會在有 throw exception的地方停下來的關係。當你不為意的時間。會在想。。為什麼程式會停下來。。  
其實可能是因為 **visual studio** 在  執行那些程式碼上**throw 了exception**停下來。自己又沒有為意

解決方法十分簡單  
我們只要在 Visual Studio Throw Exception &#8220;**Exception was unhandled by user code**&#8221; 這個popup上  
<img class="alignnone size-full wp-image-3818" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/01/BreakWhenThisExceptionTypeIsUser-handled.png?resize=479%2C408" alt="Break When This Exception Type Is User handled" width="479" height="408" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/01/BreakWhenThisExceptionTypeIsUser-handled.png?w=479 479w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/01/BreakWhenThisExceptionTypeIsUser-handled.png?resize=300%2C256 300w" sizes="(max-width: 479px) 100vw, 479px" data-recalc-dims="1" />  
**untick**了 &#8220;<span style="color: #ff0000;"><strong>Break when this exception type is user-unhandled</strong></span>&#8221;  
下次再遇到同樣的exception時便會繼續執行

Hope you find it useful