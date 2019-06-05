---
id: 2879
title: '.net Get Class Name &#8211; 怎樣在.Net上取得當前的Class的名稱'
date: 2013-05-17T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2879
permalink: '/2013/05/net-get-class-name-%e6%80%8e%e6%a8%a3%e5%9c%a8-net%e4%b8%8a%e5%8f%96%e5%be%97%e7%95%b6%e5%89%8d%e7%9a%84class%e7%9a%84%e5%90%8d%e7%a8%b1/'
categories:
  - .Net Tips And Tricks
---
今天在公司上幫同事整理一個**Project**  
因為他太懶惰了關係  
沒有好好的在所有**Try and Catch block** 上  
**Catch** 了 **Exception** 後把 這個**Exception**的資訊  
加入去資料庫內.. 以方便查詢&#8230;  
和可以幫自己寫一個 **monitoring tools** 來檢查程式上的錯誤.  
為了方便了解是那一個功能和那一個Class 出現問題  
在這一個**Error Log** 的功能上會加入一些 程式碼去顯示  
這個**Error Log** 是從那一個Class 發出的&#8230;

在之前..我使用了一個比較愚蠢的方法..  
就是在這個**Class**上定義一個變數用來記下**Class**名的

但是早近終於找到一個比較好的解決方法

**解決方法**:

我們可以使用<span style="color: #008000;"><strong> this.GetType().Name</strong></span> 取得當前的Class的名稱  
來找出現有**Object**的 **Class Name**

**E.G.**

[csharp]

string className = this.GetType().Name;

Console.WriteLine(className);  
[/csharp]

Happy Coding =)