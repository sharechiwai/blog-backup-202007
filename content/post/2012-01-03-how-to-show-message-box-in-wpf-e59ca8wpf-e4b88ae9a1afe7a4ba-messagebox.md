---
id: 2219
title: 'How to show Message Box in WPF &#8211; 在WPF 上顯示 MessageBox'
date: 2012-01-03T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2219
permalink: '/2012/01/how-to-show-message-box-in-wpf-%e5%9c%a8wpf-%e4%b8%8a%e9%a1%af%e7%a4%ba-messagebox/'
categories:
  - WPF
---
今天嘗試在WPF的中彈出使用**MessageBox.Show()** 來彈出一個**Message Box**出一個來問用戶是否執行之後的動作..  
誰不知 當我嘗試使用**MessageBox.Show()** 時&#8230; 出現了**Error Message**

經過一段時間的Research 發現要使用**System.Windows** 的 **namespace** 才可以使用**MesssageBox.Show**這個程式碼  
**溫馨提示:**  
如果你的程式上有很多**Windows** 的話.. 可以在第一個Argument 上轉入 &#8220;**Application.Current.MainWindows**&#8221; 來指定 他是從 **MainWindows**上彈出  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7eac8a4cad2e416c8d0953694bd371f1" alt="System.Windows.MessageBox.Show Signature" width="1163" height="106" />  
E.G.

[csharp]  
System.Windows.MessageBox.Show(App.Current.MainWindow, "Pop up Message", "Windows Title ",MessageBoxButton.YesNo, MessageBoxImage.Information, MessageBoxResult.Yes );

System.Windows.MessageBox.Show(Application.Current.MainWindow, "你是否繼續執行下面的動作", "Are You Sure", MessageBoxButton.YesNo);  
[/csharp]

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2081bd4128024ed5a40e1a660788f76f" alt="WPF Popup Message via MessageBox.Show" width="266" height="180" />  
Hope you find it useful