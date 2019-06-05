---
id: 961
title: 'VB.Net Get Number from String &#8212;VB.Net從String 找出數字'
date: 2010-11-16T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=961
permalink: /2010/11/vb-net-get-number-from-string/
categories:
  - .Net Tips And Tricks
  - CodePlex
  - ShareChiWaiLib
---
今天在更新**ShareChiWaiLib** 中的**XLSXHelper** 時 想到一個新的功能.. 就是令到使用者可以自定加入一些**Excel Cells** 只要他們知道..想加的**Excel 單元格**的位置便可  
例如: A2, X10等等&#8230;  
由於**Microsoft.Office.Interop.Excel** 是以**Column index** 和**Row Index** 來決定 單元格中的位置&#8230; 所以便要想辦法分析開**英文字母的是Column Index 而數字是Row Index..**

經過一段時間的Research&#8230;終於找到了一個算是有效率的方法解決這個問題&#8230;  
就是使用**Regular Expression** 常規表達式來找出數字出來&#8230;

**解決方法**:  
常規表達式中 **d** 是指 數字  
而我們會包含有小數位的數字  
所以我們的**Regular Expression** 會是這樣的  
**d\*[.]d\*|d+**  
以下是我所寫的程式碼&#8230;

[vb]  
Public Shared Function Get_NumberFromString(ByVal SourceString As String) As String  
&#8216;Regular Expression for Number  
Dim RegExpress As New Regex("(d\*[.]d\*|d+)")  
&#8216;Return the first match group  
Return RegExpress.Match(SourceString).Groups(0).Value  
End Function  
[/vb]

這個功能已經加入了**ShareChiWaiLib** 中的**StringFunc Helper Class** 中  
歡迎大家Download 來使用 和留言給我一些建議..怎麼可以令到這個Library 更有用等等

**ShareChiWaiLib**  
[http://sharechiwailib.codeplex.com/](http://sharechiwailib.codeplex.com/ "ShareChiWaiLib")

**Download 地點**  
[http://sharechiwailib.codeplex.com/releases/](http://sharechiwailib.codeplex.com/releases/ "ShareChiWaiLib Release ")

**例子:**

[vb]  
Dim Num as String = ShareChiWaiLib.StringFunc.Get_NumberFromString("ShareChiWai 1115.01 Blog Post")  
MessageBox.Show(Num)  
[/vb]

這會出現 &#8220;**1115.01**&#8221; 這個Popup Message

Hope you find it useful