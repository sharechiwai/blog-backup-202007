---
id: 2295
title: 'WinForm 捕獲鍵盤按鍵事件問題 &#8211; WinForm unable to capture keypress event'
date: 2012-01-17T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2295
permalink: '/2012/01/winform-%e6%8d%95%e7%8d%b2%e9%8d%b5%e7%9b%a4%e6%8c%89%e9%8d%b5%e4%ba%8b%e4%bb%b6%e5%95%8f%e9%a1%8c-winform-unable-to-capture-keypress-event/'
categories:
  - .Net Tips And Tricks
tags:
  - WinForm
---
今天有朋友問..他希望可以捕獲鍵盤按鍵事件 但是不知道為什麼 在**Event Handler** 上寫了程式碼..但是都沒有反應&#8230; 都是沒有trigger **KeyPress**這個**Event**

經過一段時間測試之後終於找到是什麼原因了

**解決方法**:

我們需要設定**KeyPreview**為**True**才可以令**Form_keypress/keyup/keydown**等等的 添加相应的代码執行的

E.G.  
**C Sharp**

[csharp]  
private void Form1_Load(object sender, EventArgs e)

{

this.KeyPreview = true;

}  
[/csharp]

Hope you find it useful