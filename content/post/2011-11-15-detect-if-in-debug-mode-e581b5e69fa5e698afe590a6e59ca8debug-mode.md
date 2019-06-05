---
id: 2184
title: 'Detect if in Debug mode &#8211; 偵查是否在Debug mode'
date: 2011-11-15T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2184
permalink: '/2011/11/detect-if-in-debug-mode-%e5%81%b5%e6%9f%a5%e6%98%af%e5%90%a6%e5%9c%a8debug-mode/'
categories:
  - .Net Tips And Tricks
---
今天有朋友問.. 有沒有方法可以在開發過程中可以令**Visual Studio** 選擇一種設定變數, 我知道在Web Project上是可以用&#8221;**Configuration Manager**&#8220;來建立不同的**Profile** 在不同模式上使用不同的**Profile**

有機會的話我會建立一個**Sample**和大家分享

如果你的不是**Web Project** 或想在使用**Visual Studio**時[不在**Production** mode] 使用另一些 設定的話可以參考以下的程式碼

**解決方法**:

我們可以用<span style="color: #339966;"><strong> System.Diagnostics.Debugger.IsAttached</strong></span> 來看看 執行的程式有沒有附加 Debugger  
E.G.  
**C#**

[csharp]  
if (System.Diagnostics.Debugger.IsAttached)  
{  
MessageBox.Show("Development Mode");  
}  
else  
{  
MessageBox.Show("Production Mode");  
}  
[/csharp]

Hope you find it useful