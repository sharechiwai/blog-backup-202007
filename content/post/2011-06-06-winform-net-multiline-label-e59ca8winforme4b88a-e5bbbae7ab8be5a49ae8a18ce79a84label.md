---
id: 1802
title: 'WinForm .net Multiline Label &#8211; 在WinForm上 建立多行的Label'
date: 2011-06-06T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1802
permalink: '/2011/06/winform-net-multiline-label-%e5%9c%a8winform%e4%b8%8a-%e5%bb%ba%e7%ab%8b%e5%a4%9a%e8%a1%8c%e7%9a%84label/'
categories:
  - .Net Tips And Tricks
---
在改善自己所建造的程式其間發現&#8230;  
需要在**WinForm**上提供更多的資訊給使用者  
(因為之前這個程式多數是我運作的..  
但是為了**Usability**..我們應該好好設計這程式  
令到程式更容易使用..使用者更容出易明白每一個功能是用來做什麼的&#8230;ETC)  
所以我便在**Form** 上面加入了一些**Label** 控件..  
用來顯示一些操作提示..  
之後發現到原來**Label Control** 是沒有**Wrap text 自動轉行的功能**的  
[<img class="alignnone" title="Single line Label" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/75d7dec0de504facb3704d3c4f533292/renditions/fullsize.jpg?resize=552%2C232" alt="" width="552" height="232" data-recalc-dims="1" />](https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/75d7dec0de504facb3704d3c4f533292/renditions/fullsize.jpg)  
那麼我們便要手動將文字分行了  
但是怎樣可以令到文字顯示在多行呢? 怎樣做到Multiline Label 的效果?

**解決方法:**  
在**IDE (Visual Studio)**上可以選取將要顯示多行字的**Label**  
之後在**Properties Windows** 上按一下 &#8220;**Text Property / 文字屬性**&#8221;  
[<img class="alignnone" title="Properties Windows - Label Control Text Properties" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d9320df61dd0466a89b3c1da630cd643/renditions/fullsize.jpg?resize=433%2C336" alt="" width="433" height="336" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d9320df61dd0466a89b3c1da630cd643/renditions/fullsize.jpg)  
之後你便可以看到一個 像**Drop Down List的 三角形下拉箭頭**&#8230;  
按一下便可以在這個**Text Area** 上輸入 **Multiline** 多行的文字了  
[<img class="alignnone" title="Label Text Properties allow to add Multiline text" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e3bf08487dde4ceeb13c41b4990e834e/renditions/fullsize.jpg?resize=420%2C338" alt="" width="420" height="338" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e3bf08487dde4ceeb13c41b4990e834e/renditions/fullsize.jpg)

如果你想在Code 上做到**Multiline Label**的效果你可以  
**C #** 可以使用 &#8220;**\n**&#8221; 來作隔行的 字串

[csharp]  
lbl_ShareChiWai.Text = "Hello! How are you doing? \nwelcome to http://blog.sharechiwai.com. \n\nHope you like this Blog";  
[/csharp]

**VB** 可以使用 **vbCrLf, vbLf** 和 **Environment.NewLine**

[vb]  
lbl_ShareChiWai.Text = "Hello! How are you doing?" & vbLf & "welcome to http://blog.sharechiwai.com." & Environment.NewLine & vbCrLf & "Hope you like this Blog"  
[/vb]

[<img class="alignnone" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/50b44b20f6664bdc988d08cd4b874525/renditions/fullsize.jpg?resize=581%2C204" alt="Multiine Label" width="581" height="204" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/50b44b20f6664bdc988d08cd4b874525/renditions/fullsize.jpg)  
Hope you find it useful

&nbsp;