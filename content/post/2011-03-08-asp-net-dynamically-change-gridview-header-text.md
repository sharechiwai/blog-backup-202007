---
id: 830
title: ASP.NET Dynamically change GridView Header Text
date: 2011-03-08T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=830
permalink: /2011/03/asp-net-dynamically-change-gridview-header-text/
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
今天公司需要更改公司的網站上**GridView Header上的 內容**.

之前以為解決方法很簡單的..  
只是在**DataBinding** 後  
使用更改**Header** 的Code 便可  
E.G.  
**VB.Net**

[vb]  
ShareChiWai_GridView1.Columns(1).HeaderText="New Column Header Content"  
[/vb]

C#

[csharp]  
ShareChiWai_GridView1.Columns[1].HeaderText="New Column Header Content";  
[/csharp]

可惜不能成功..

最後終於找到了解決放法了&#8230;  
我們需要建立一個**GridView RowCreated Event**  
之後檢查現在的Row類型是不是 **DataControlRowType.Header** 類

如果是的話便使用以下的Code 來更改內容..  
**<span style="color: #008000;">e.Row.Cells(ColumnID).Text =&#8221;新的Column Header&#8221;</span>**

**解決方法:**

**VB.Net**

[vb]  
Protected Sub gv\_ShareChiWai\_RowCreated(ByVal sender As Object, ByVal e As System.Web.UI.WebControls.GridViewRowEventArgs) Handles gv_ShareChiWai.RowCreated  
If (e.Row.RowType = DataControlRowType.Header) Then  
e.Row.Cells(6).Text = "中文內容"  
e.Row.Cells(8).Text = "第8行"  
End If  
End Sub  
[/vb]

**C#**

[csharp]  
protected void gv\_ShareChiWai\_RowCreated(object sender, System.Web.UI.WebControls.GridViewRowEventArgs e)  
{  
if ((e.Row.RowType == DataControlRowType.Header)) {  
e.Row.Cells[6].Text = "中文內容";  
e.Row.Cells[8].Text = "第8行";  
}  
}

[/csharp]

Hope you find it useful

&nbsp;