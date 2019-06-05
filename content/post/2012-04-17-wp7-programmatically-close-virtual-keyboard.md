---
id: 2357
title: WP7 programmatically close virtual Keyboard
date: 2012-04-17T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2357
permalink: /2012/04/wp7-programmatically-close-virtual-keyboard/
categories:
  - Window Phone Development
---
今天在開發一個**WP7**程式時發現一個小小的問題&#8230;  
我的程式有一個**Search Box**..  
當使用者輸入了想搜尋的東西&#8230;  
之後按**Application Bar**上的按鈕..  
便在Search Box下面的**TextBox**上出現資料  
但是很可惜&#8230;當你輸入資料到Search Box之後按**Application Bar**的按鈕後&#8230;  
**WP7**都仍然顯示 他的**Virtual Keyboard**  
阻外使用者觀察結果&#8230;  
感覺十分不方便&#8230;

嘗試了很多方法都不知道怎樣可以**Off Focus** 剛剛輸入完搜尋的東西的**TextBox**  
最後在網上做了一會兒 research 之後終於找到了解決方法了

**解決方法**:  
只要在想程式碼最後端 [按鈕會執行的程式碼]  
加入以下的Code

[csharp]  
this.Focus();  
[/csharp]

便可以了&#8230;**this.Focus()** 是用來把**focus**轉到程式的Page/頁上的  
加入了程式碼後  
按完**Application Bar**上的按鈕..這個**Virtual Keyboard**便自已慢慢退出了  
Hope you find it useful