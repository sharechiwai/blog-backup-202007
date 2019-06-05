---
id: 540
title: 'VB.net Create Button Dynamically&#8212;VB.Net 用程式碼建立按鈕'
date: 2010-08-31T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=540
permalink: '/2010/08/vb-net-create-button-dynamically-vb-net-%e7%94%a8%e7%a8%8b%e5%bc%8f%e7%a2%bc%e5%bb%ba%e7%ab%8b%e6%8c%89%e9%88%95/'
jabber_published:
  - "1283184036"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982584";}";'
categories:
  - .Net Tips And Tricks
---
今日有朋友問, 如何可以用程式碼建立按鈕,之前在Silverlight 都試過這樣做&#8230; 但由於之前的知識/經驗都比較淺, 所以都不明白其概念&#8230;

今天經過一段時間的試驗.終於明白了

今天會用一個簡單的計算機介面來做一個教學,如果你遇到差不多的問題時, 希望這會有幫助

首先當然是要建立一個新的**WinForm**  
我叫他做&#8221;**ShareChiWaiCalculator.vb**&#8221;

之後在這個**WinForm**的上端 加入一個 **TextBox** 和**Button**  
**TextBox** 的名稱是 &#8220;**txt_CalculateValue**&#8221;  
這是用來儲存使用者經過按鈕按下的數字的  
為了令這個**TextBox**更像 平常的 計算機  
我把**txt_CalculateValue** 中的屬性入面的  
**RightToLeft** 屬性 設定成 &#8220;**True**&#8221;  
[<img class="alignnone size-full wp-image-544" title="RightToLeft" src="https://i2.wp.com/farm6.static.flickr.com/5266/5687813297_405daf3c59.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5266/5687813297_405daf3c59.jpg)  
這樣文字便會向右至左排列了

**Button** 的名稱是&#8221;**btn_Del**&#8221;  
用來讓使用者刪除**TextBox** 上的文字的

把WinForm設定好後我們便可以專心寫Code 了  
[<img class="alignnone size-full wp-image-543" title="MainForm" src="https://i1.wp.com/farm4.static.flickr.com/3036/5693803201_76496ddd91.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm4.static.flickr.com/3036/5693803201_76496ddd91.jpg)

我會建立一個功能 [**CreateSimpleCalculatorButton**] 來建議**Dynamic Button** 用程式碼來建立按鈕的

詳情可以參考下面的Code 這是所有的程式碼

[vb]  
Public Class ShareChiWaiCalculator

&#8216;建立了一個按鈕給大家刪去一些在txt_CalculateValue的文字  
Private Sub btn\_Del\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btn_Calculate.Click  
If txt_CalculateValue.Text.Length > 0 Then  
txt\_CalculateValue.Text = txt\_CalculateValue.Text.Substring(0, txt_CalculateValue.Text.Length – 1)  
End If

End Sub

Public Sub CreateSimpleCalculatorButton()  
&#8216;建立 坐標位置的變數, 方便一會兒安排 自動生產的button 的位置  
Dim y As Integer = 10  
Dim x As Integer = 0

&#8216; 用for loop 來建立 這些button 做 10個button  
&#8216;因為多數的計算機的數字只由下至上排列的, 所以我便用了  
&#8216;For Loop 中的Step – 1 來 建立我的動態按鈕…[比較容易一點]  
For ButtonIndex As Integer = 9 To 0 Step -1

&#8216; 建造新的 button  
Dim CalculatorButton As New Button  
&#8216;設定這新的button 的闊度  
CalculatorButton.Width = 35  
&#8216;設定這新的button 的高度  
CalculatorButton.Height = 35

&#8216;我們暫定每行有3個BUTTON, 當每行有多個4個BUTTON 時重設行距, 令到下一行的和這一行的距離有10 個PIXEL  
&#8216; 和重設x 坐標\` = 0, 令到位置由頭開始

If ButtonIndex Mod 3 = 0 Then  
&#8216;設定 TOP 的 坐標位置令他可以和上一排的有10個PIXEL 的距離  
y += CalculatorButton.Height + 10  
x = 0  
End If

&#8216;設定文字 和 位置  
CalculatorButton.Text = ButtonIndex

&#8216;設定 TOP 的 坐標位置  
CalculatorButton.Top = y  
&#8216;下面的CODE 可以令到這個BUTTON 和另一個BUTTON 有5個PIXEL 的距離  
CalculatorButton.Left = 26 + (x * (CalculatorButton.Width + 5))  
x += 1  
&#8216;設定 BUTTON CLICK EVENT  
AddHandler CalculatorButton.Click, AddressOf CalculatorButton_Click

&#8216;把button 加到 form 中  
Me.Controls.Add(CalculatorButton)  
Next  
End Sub

&#8216;每當使用者按下這些按鈕時, 他便會打 按鈕上的文字寫到 上面的TextBox 上 [txt_CalculateValue]  
Private Sub CalculatorButton_Click(ByVal sender As Object, ByVal e As EventArgs)  
Dim btn As Button = sender  
txt_CalculateValue.Text &= btn.Text

End Sub

Private Sub ShareChiWaiCalculator_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
CreateSimpleCalculatorButton()  
End Sub  
End Class  
[/vb]

**大功告成**  
[<img class="alignnone size-full wp-image-542" title="Example" src="https://i0.wp.com/farm6.static.flickr.com/5303/5693803125_1868c37ffc.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5303/5693803125_1868c37ffc.jpg)

Hope you find it useful, 歡迎大家給我一些意見, 令我可以發多一些有用的文章/教學