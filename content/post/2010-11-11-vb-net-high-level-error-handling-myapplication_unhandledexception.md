---
id: 913
title: 'VB.Net High Level Error Handling MyApplication_UnhandledException &#8212; VB.Net 中使用高層次的例外/錯誤處理 MyApplication_UnhandledException'
date: 2010-11-11T05:00:16+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=913
permalink: /2010/11/vb-net-high-level-error-handling-myapplication_unhandledexception/
categories:
  - .Net Tips And Tricks
---
在上星期和顧問開會的時候..  
他問到&#8230;我們有沒有在程式上做**Error Handling**的  
大家當然說有&#8230;  
當了一段時候的**Developer**後便發覺..  
**Error Handling &#8212;用Try and Catch Statement  
**  
**處理錯誤的好處&#8230;**  
1) 可以避免程式因為一些處理上的問題出現問題之後自己**Throw Exception**之後便自動關閉&#8230;  
2) 是可以更加了解自己的程式上&#8230;  
那一個地方做很不夠好&#8230;  
或者可以做多一些驗證..會令到整個程式更加 **Robust/穩定.**..

之後他又問..我們有沒有建立一些**High Level 的 Error Handling** 的方法&#8230;  
這個問題我從來都沒有想過的&#8230;  
還以為**Try/Catch Statement** 已經後足夠&#8230;  
原來**High Level Error Handling** 是一個 在方法..  
去捕捉一些我們沒有用**Try/Catch Statement** 去處理的程式碼..  
而這些程式碼又因為一些突如其來出現的情況令到程式出現 **Application Un-handled Exception** 令到這個程式 死掉/自動關閉

今天想和大家分享我今日學會的  
**High Level Error Handling**的方法  
去處理 程式上一些沒有被處理的 錯誤..令到這程式即使出現**Application Error/ un-handled Exception**  
也不會出現**Error Message** 錯誤信息..之後自我關閉&#8230;

**方法十分簡單**

首先在程式碼上建立一些壞的Code  
E.G.

[vb]  
Dim i As Int16 = "999999999"  
[/vb]

這會出現 <span style="color: #ff0000;"><strong>&#8220;Arithmetic operation resultd in a overflow&#8221;</strong></span> 的錯誤  
因為**Int16最大可儲存的數值是 -32768 到 +32767**.

在執行的時候會出現以下的錯誤 [如我們所料]  
[<img class="alignnone size-full wp-image-921" title="Exception" src="https://i2.wp.com/farm6.static.flickr.com/5062/5688437362_7656deb326.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5062/5688437362_7656deb326.jpg)

要處理這些**Unhandled Exception** 我們可以打開這個**Project** 的&#8221;**內容/Properties**&#8221;  
在&#8221;**應用程式 /Application**&#8220;分頁  
[<img class="alignnone size-full wp-image-920" title="ApplicationScreen" src="https://i0.wp.com/farm6.static.flickr.com/5185/5688435646_241de95168.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5185/5688435646_241de95168.jpg)  
按一下&#8221;檢視應用程式事件 &#8220;**View Application Events**&#8221;  
在&#8221;**ApplicationEvent.vb**&#8221; 中 按一下Drop Down List 下拉列表 選擇 &#8220;**(My Application Events)**&#8221;  
[<img class="alignnone size-full wp-image-919" title="ApplicationEvent" src="https://i1.wp.com/farm6.static.flickr.com/5225/5688435222_2f5b0ace2e.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5225/5688435222_2f5b0ace2e.jpg)  
在&#8221;**Declarations**&#8221; Drop down List 下拉列表  選擇 &#8220;**(UnhandledException)**&#8221;  
[<img class="alignnone size-full wp-image-918" title="ApplicationEventUnhandledException" src="https://i0.wp.com/farm6.static.flickr.com/5026/5687866093_f3c27d89e8.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5026/5687866093_f3c27d89e8.jpg)

之後便會自己產生 像以下一樣的程式碼  
[<img class="alignnone size-full wp-image-917" title="ExceptionOrigCode" src="https://i1.wp.com/farm6.static.flickr.com/5188/5688437478_d9011377a5.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5188/5688437478_d9011377a5.jpg)  
之後我們便可以加入自己的**Code** 來 作一個比較  
**高層次的Error Handling**去處理一些忘了處理或突如其來 的**Exception** 了

以下是我用來作示範的程式碼

[vb]

Private Sub MyApplication_UnhandledException(ByVal sender As Object,  
ByVal e As Microsoft.VisualBasic.ApplicationServices.UnhandledExceptionEventArgs) Handles Me.UnhandledException

&#8216;e.Exception.GetType().ToString  
&#8216; 是用來顯示錯誤的類型  
&#8216;e.Exception.Message  
&#8216;用來顯示錯誤信息  
&#8216;e.Exception.StackTrace  
&#8216;顯示詳情錯誤資訊&#8230;Stack Trace  
MessageBox.Show("錯誤信息: " & vbNewLine &  
e.Exception.StackTrace,  
"程式錯誤 &#8212; " & e.Exception.GetType().ToString & " &#8212; " & e.Exception.Message,  
MessageBoxButtons.OK,  
MessageBoxIcon.Error)  
&#8216;e.ExitApplication = False 是用來停止程式自動關閉的  
&#8216; = True 當遇到 MyApplication_UnhandledException 時會自動關閉程式  
e.ExitApplication = False  
End Sub

[/vb]

或者你可以更改一下把錯誤信息寫進  
文字檔或資料庫上 或者是Email 自己&#8230;  
而我這個例子都是把這個錯誤信息轉成一個  
Message Box 顯示一些錯誤資料給我看 =)  
[<img class="alignnone size-full wp-image-916" title="Overflow" src="https://i2.wp.com/farm6.static.flickr.com/5250/5688438042_ae955005a4.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5250/5688438042_ae955005a4.jpg)

Hope you find it useful