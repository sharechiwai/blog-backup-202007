---
id: 2619
title: 'Show Number of record on DataGridView &#8211; 在DataGridView上顯示有多小條數據'
date: 2012-11-28T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2619
permalink: '/2012/11/show-number-of-record-on-datagridview-%e5%9c%a8datagridview%e4%b8%8a%e9%a1%af%e7%a4%ba%e6%9c%89%e5%a4%9a%e5%b0%8f%e6%a2%9d%e6%95%b8%e6%93%9a/'
categories:
  - .Net Tips And Tricks
---
在改善自己之前寫的程式的使用者體驗時發現原來如果可以在Form上顯示**DataGridView**/**Table**上有多小個資料&#8230;使用者會感到很有用的

今天想和大家介紹如何顯示/更新**DataGridView** 上有多小條數據

**解決方法**:  
我們可以使用**DataBindingCompleted** 這個**Event**..每當**DataGridView**的**Data source list** 更新了之後便會**Trigger** 這個Event了  
之後我們便可以用**DataGridView**.**RowCount**這個property來找出這個**DataGridView**上有多小條數據了

**E.g.  
C#**

[csharp]

private void dgv\_FileList\_DataBindingComplete(object sender, DataGridViewBindingCompleteEventArgs e)  
{  
lblNoOfRecords.Text = dgv_FileList.RowCount.ToString();  
}

[/csharp]

Hope you find it useful