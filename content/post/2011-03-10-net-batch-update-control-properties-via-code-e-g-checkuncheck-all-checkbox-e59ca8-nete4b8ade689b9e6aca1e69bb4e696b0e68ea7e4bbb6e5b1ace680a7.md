---
id: 1699
title: '.Net Batch Update Control Properties via Code E.G. Check/UnCheck All CheckBox &#8211; 在.Net中批次更新控件屬性'
date: 2011-03-10T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1699
permalink: '/2011/03/net-batch-update-control-properties-via-code-e-g-checkuncheck-all-checkbox-%e5%9c%a8-net%e4%b8%ad%e6%89%b9%e6%ac%a1%e6%9b%b4%e6%96%b0%e6%8e%a7%e4%bb%b6%e5%b1%ac%e6%80%a7/'
categories:
  - .Net Tips And Tricks
---
已經忘了之前有沒有把這個筆記寫好和發到網誌上了&#8230;  
今天想和大家分享的技術是用來批次更新 控件屬性的..  
有時候使用這個方法十分方便  
E.G.  
有時候你可能會建立一個按鈕給使用者**Check/Uncheck** 所有**CheckBox**的  
或者需要設定在某一個**GroupBox**內的 **TextBox** 屬性變成Enable = False等等

**解決方法十分簡單&#8230;**  
在可以的情況下.  
所相同性質的控件..放在**GroupBox**或**Panel**中..  
以便管理..  
E.G.  
我建立一個**Panel** 改名為&#8221;p**_ReportSettings**&#8221;  
入面建立了很多的**CheckBox**..用來設定那一個Report將會被Generate

之後在**Panel**外建立另一個**CheckBox**來 作**Check/Uncheck All CheckBox**之用  
之後便可以加入以下的Code用來找出所有在**Panel** 入有**CheckBox** 屬性 的控件出來了  
E.G.

**VB.Net**

[vb]  
Private Sub cb\_ReportCheckAll\_CheckedChanged(sender as Object, e as EventArgs) _  
Handles cb_ReportCheckAll.CheckedChanged

Dim CheckAll As Boolean = Not cb_ReportCheckAll.Checked

For Each c In pl_ReportSettings.Controls  
If TypeOf (c) Is CheckBox Then  
CType(c, CheckBox).Checked = CheckAll  
End If

Next  
End Sub  
[/vb]

**C#**

[csharp]  
private void cb\_ReportCheckAll\_CheckedChanged(object sender, EventArgs e)  
{

bool CheckAll = !cb_ReportCheckAll.Checked;

foreach (object c\_loopVariable in pl\_ReportSettings.Controls) {

if ((c_loopVariable) is CheckBox) {  
((CheckBox)c_loopVariable).Checked = CheckAll;  
}

}  
}  
[/csharp]

Hope you find it useful