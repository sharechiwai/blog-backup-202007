---
id: 25
title: 'How to add CheckBox into DataGridView &#8212; 如何在DataGridView 中添加 CheckBox'
date: 2010-08-15T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=25
permalink: /2010/08/how-to-add-checkbox-into-datagridview/
jabber_published:
  - "1281818332"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282677963";}";'
categories:
  - .Net Tips And Tricks
---
最近有朋友問我如何在**DataGridView** 中添加 **CheckBox**,  
這可以方便用戶選擇那一行需要更新  
其實在**DataGridView** 中添加 **CheckBox** 是很簡單的

我們可以用 **DataGridViewCheckBoxColumn** Class  
來建立一個 **DataGridViewCheckBoxColumn**  
然後再把 **DataGridViewCheckBoxColumn** 加進到 現有的**DataGridView** 上便可

E.G.  
假設我們有一個**DataGridView** 叫 DataGridView1  
當我們把他綁定了資料庫後  
便可以用以下的Code 找到這個DataGridView 有多少Column

[vb]  
Dim NewColumnIndex As Integer = DataGridView1.Columns.Count &#8216;取得有多少Column  
DataGridView1.Columns.Insert(DataGridView1.Columns.Count, New DataGridViewCheckBoxColumn)  
&#8216;在DataGridView 的最後一行插入一個DataGridViewCheckBoxColumn  
DataGridView1.Columns(NewColumnIndex).HeaderText = "New Column"  
&#8216;最後當然要給與這個Column 一個名字, 放便了解 / 不加也可以  
[/vb]

Hope you find it useful