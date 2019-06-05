---
id: 569
title: 'VB.Net Use BackgroundWorker To Improved User Experience &#8212; VB.Net 使用 BackgroundWorker 增加使用者經驗上'
date: 2010-09-03T06:00:47+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=569
permalink: '/2010/09/vb-net-use-backgroundworker-to-improved-user-experience-vb-net-%e4%bd%bf%e7%94%a8-backgroundworker-%e5%a2%9e%e5%8a%a0%e4%bd%bf%e7%94%a8%e8%80%85%e7%b6%93%e9%a9%97%e4%b8%8a/'
jabber_published:
  - "1283464848"
email_notification:
  - "1283464849"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982590";}";'
categories:
  - .Net Tips And Tricks
---
大家有沒有試過在**WinForm** 中, 需要處理一些比較繁複的**Process**  
或要使用到**WebService**/ 要在**Database** 中 處理一些需時比較長的**Query**

如果有的話, 相信大家都會在**WinForm 遇到Hang/ 沒有回應 [No response]** 的現像  
今日的網誌想向大家介紹一個方法, 可以解決這個問題的  
解決需要處理一些比較繁複的**Process**  
程式會 Hang/ 沒有回應 [No response] 的現像  
令使用者可以繼續使用 這個Win Form 中的其他功能&#8230;

由於沒有一個大的**Database**給我嘗試 模擬 **資料庫存取時的Delay**  
所以在這裡我會用一個**For Loop** 來模擬 資料庫存取時的Delay/  
或電腦在運作一些十分複雜的程式碼時**WinForm沒有回應的情況**

首先我們建立一個新的**WinForm**  
之後建立**2個Button**  
放便之後做試驗  
第一個Button 叫  
**btn_LongProcess**  
-我們會用這個Button來進行資料庫存取時的Delay 令到WinForm沒有回應的情況  
另一個Button 叫  
**btn_NormalProcess**  
-用來當作一些正常的WinForm動作E.G. 一些很快得到回應的動作  
在這個Example我用他來做一個**MessageBox** PopUp

之後可以在右手面的**工具列**[**Toolbox**] 的&#8221;**All Windows Forms**&#8221; Section 上  
把**BackgroundWorker** 拖曳到你的WinForm中  
[<img class="alignnone size-full wp-image-574" title="BGWorker" src="https://i2.wp.com/farm6.static.flickr.com/5244/5688389494_4ae51485ff.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5244/5688389494_4ae51485ff.jpg)

之後便可以設定這個**BackgroundWorker** 的**屬性** 了  
通常我都會把他的名稱改成**bg_Worker** 放便使用  
[<img class="alignnone size-full wp-image-572" title="BGProperty1" src="https://i2.wp.com/farm6.static.flickr.com/5182/5688389220_37919df2a1.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5182/5688389220_37919df2a1.jpg)

**BackGroundWorker 屬性**  
**WorkerReportsProgress** -是用來設定這個BackgroundWorker會否匯報他的進度  
**WorkerSupportsCancellation** &#8212; 用來設定這個BackgroundWorker能不能支援取消這個動作

**BackGroundWorker Event**  
**BackGroundWorker** 有三個 Event  
**DoWork, ProgressChanged, RunWorkerCompleted**

**DoWork** &#8211; 這是最主要的Event 因為我們主要是使用**BackGroundWork** 的**DoWork** **Event** 來幫我們做事的, 我們可以把要執行的功能放住這個, 用他來幫我們執行一些比較複雜/會令到WinForm顯示沒有回應的功能 這個BackGroundWorker 可以幫我們把這些程序在背後執行, 所以這便可以避免WinForm假死了

**ProgressChanged** &#8211; 我們可以用**ProgressChanged Event** 來匯報在**DoWork** Event 執行的進度[要把**WorkerReportsProgress**屬性設定成**True** 才可以使用這個Event 的 ]  
**RunWorkerCompleted** &#8211; 當DoWork Event 執行的 程序完成時 **RunWorkerCompleted Event** 就會被執行  
我們可以在這三個Event上用Double Click, 去建立這三個Event 的程式碼  
[<img class="alignnone size-full wp-image-573" title="BGProperty2" src="https://i0.wp.com/farm6.static.flickr.com/5189/5687819807_47cb8e51e4.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5189/5687819807_47cb8e51e4.jpg)

**ProgressChanged**, **RunWorkerCompleted** 和**WorkerSupportsCancellation** 會在將來的網誌上加以說明

設定好介面後我們終端機可以開始寫程式碼了  
在**WinForm**中Double Click, 令我們開啟 **Form_Load** Event

**Control.CheckForIllegalCrossThreadCalls = False** 去解決Cross Thread Operation , 如果不加這句的話當

你的**BackGroundWorker** 在作時,如果你按你**WinForm**上的任何一個控制, 他可能會發出錯誤信息的  
E.G.

[vb]  
Private Sub ShareChiWaiBGWorker_Load(ByVal sender As System.Object, ByVal e As System.EventArgs)Handles MyBase.Load

Control.CheckForIllegalCrossThreadCalls = False &#8216;要這樣才可以解決Cross Thread Operation的問題  
End Sub  
[/vb]

在**btn_NormalProcess** 的**Click Event** 中  
加入以下程式碼, 當使用者按下**btn_NormalProcess** 時, 他會**PopUp** 現時的時間

&nbsp;

[vb]  
Private Sub btn\_NormalProcess\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)Handles btn_NormalProcess.Click  
MsgBox(Now)  
End Sub  
[/vb]

以下是我寫的用來擬一些**Long Process**的Code

[vb]  
Public Sub LongProcess() &#8216;用來模擬一些Long Process的Code  
Dim info As Integer = 0  
For i As Integer = 0 To 999999  
For j As Integer = 0 To 99999  
info = i + j  
Next  
Next  
btn_LongProcess.Text = Now &#8216;完成時候 Update 這個Button 的文字為現在的時間  
End Sub  
[/vb]

在**btn_LongProcess** 的**Click Event** 中  
如果我們直接執行這個**LongProcess()** method 你的WinForm 應該會出現沒有回應的  
E.G.

[vb]  
Private Sub btn\_LongProcess\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)Handles btn_LongProcess.Click  
LongProcess()  
End Sub  
[/vb]

&#8211;我們可以測試一下沒有用**BackGroundWorker**時 的情況應該會出現沒有回應的

所以我們可以用以把 LongProcess() 這個功能放進bg_Worker.DoWork Event中  
待這個BackGroundWorker 幫我們執行LongProcess()  
E.G.

[vb]  
Private Sub bg\_Worker\_DoWork(ByVal sender As System.Object, ByVal e As System.ComponentModel.DoWorkEventArgs) Handles bg_Worker.DoWork  
LongProcess()  
End Sub  
[/vb]

之後我們可以更改我們的btn_LongProcess 的Click Event

[vb]  
Private Sub btn\_LongProcess\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)Handles btn_LongProcess.Click  
If Not bg_Worker.IsBusy Then &#8216;查看BackGroundWorker是不是正成忙碌中, 如果不是的話便執行  
bg_Worker.RunWorkerAsync()  
End If  
End Sub  
[/vb]

現在可以再測試一下, 沒有回應的情況應該不會出現了, 而且使用都可以任意凡移動這個WinForm和按下**btn_NormalProcess** 時會看到現時的時間  
[<img class="alignnone size-full wp-image-575" title="NormalProcess" src="https://i0.wp.com/farm6.static.flickr.com/5261/5687826579_3a7f3182d9.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5261/5687826579_3a7f3182d9.jpg)

LongProcess完成了  
[<img class="alignnone size-full wp-image-576" title="Completed" src="https://i0.wp.com/farm6.static.flickr.com/5285/5687820541_aa2cd3f7c7.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5285/5687820541_aa2cd3f7c7.jpg)

這證明了BackGroundWorker 可以解決WinForm 在執行一些比較,需時的程序時出現沒有回應的情況

將來的網誌我會說說**ProgressChanged, RunWorkerCompleted 和WorkerSupportsCancellation** 的用法和如果好好運用**BackGroundWorker**去增加使用者經驗

Hope you find it useful, 歡迎大家給我一些意見, 令我可以發多一些有用的文章/教學,Improve 自己

**全部的原始碼**

[vb]  
Public Class ShareChiWaiBGWorker

Private Sub bg\_Worker\_DoWork(ByVal sender As System.Object, ByVal e As System.ComponentModel.DoWorkEventArgs) Handles bg_Worker.DoWork  
LongProcess()  
End Sub

Private Sub bg\_Worker\_ProgressChanged(ByVal sender As System.Object, ByVal e As System.ComponentModel.ProgressChangedEventArgs) Handles bg_Worker.ProgressChanged

End Sub

Private Sub bg\_Worker\_RunWorkerCompleted(ByVal sender As System.Object, ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs) Handles bg_Worker.RunWorkerCompleted

End Sub

Private Sub ShareChiWaiBGWorker_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
Control.CheckForIllegalCrossThreadCalls = False &#8216;要這樣才可以解決Cross Thread Operation 的問題  
End Sub

Public Sub LongProcess() &#8216;用來模擬一些Long Process的Code  
Dim info As Integer = 0  
For i As Integer = 0 To 999999  
For j As Integer = 0 To 9999  
info = i + j  
Next  
Next  
btn_LongProcess.Text = Now &#8216;完成時候 Update 這個Button 的文字為現在的時間  
End Sub

Private Sub btn\_LongProcess\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btn_LongProcess.Click  
If Not bg_Worker.IsBusy Then &#8216;查看BackGroundWorker是不是正成忙碌中, 如果不是的話便執行  
bg_Worker.RunWorkerAsync()  
End If  
End Sub

Private Sub btn\_NormalProcess\_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btn_NormalProcess.Click  
MsgBox(Now)  
End Sub  
End Class  
[/vb]