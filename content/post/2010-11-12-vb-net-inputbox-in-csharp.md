---
id: 905
title: 'VB.Net InputBox in CSharp &#8212; 在C Sharp 中使用 InputBox'
date: 2010-11-12T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=905
permalink: /2010/11/vb-net-inputbox-in-csharp/
categories:
  - .Net Tips And Tricks
---
<div id="_mcePaste">
  之前和大家分享了一個十分好用的<strong>InputBox</strong>&#8230;
</div>

<div id="_mcePaste">
  <a title="How to create a pop up box to Prompt for User input in WinForm --- 如果在WinForm 中建立一個彈出視窗 收集使用者輸入的資料" href="http://blog.sharechiwai.com/2010/11/inputbox">How to create a pop up box to Prompt for User input in WinForm &#8212; 如果在WinForm 中建立一個彈出視窗</a> 收集使用者輸入的資料
</div>

<div id="_mcePaste">
  有朋友問..在<strong>C Sharp</strong> 後像用不到這個 功能&#8230;
</div>

<div id="_mcePaste">
  其實是可以的&#8230;
</div>

<div id="_mcePaste">
  但要做多一些事&#8230; 十分簡單
</div>

<div id="_mcePaste">
  解決方法
</div>

<div id="_mcePaste">
  如果想在 C# 中使用某些VB.Net 獨有的功能
</div>

<div id="_mcePaste">
  大家可以你的 <strong>C# Project</strong> 上
</div>

<div id="_mcePaste">
  按右鍵&#8221;<strong>加入參考 /Add References</strong>&#8220;
</div>

<div id="_mcePaste">
  在<strong>&#8220;.Net &#8221; 分頁</strong>中
</div>

<div id="_mcePaste">
  選擇 &#8220;<strong>Microsoft.VisualBasic</strong>&#8220;
</div>

<div id="_mcePaste">
  之後按&#8221;<strong>確定/OK</strong>&#8221;<br /> <a href="https://i2.wp.com/farm6.static.flickr.com/5068/5687869457_22d7a488e4.jpg"><img class="alignnone size-full wp-image-910" title="VBDLL" src="https://i2.wp.com/farm6.static.flickr.com/5068/5687869457_22d7a488e4.jpg?resize=561%2C446" alt="" width="561" height="446" data-recalc-dims="1" /></a>
</div>

<div id="_mcePaste">
  大家可以在 你想使用這些VB 功能的 Class
</div>

<div id="_mcePaste">
  加入 參考 E.G.
</div>

<div id="_mcePaste">
  <strong><span style="color: #008000;">Using Microsoft.VisualBasic;</span></strong>
</div>

<div id="_mcePaste">
  你便可以通過<strong> Interaction Class</strong> 來使用 <strong>InputBox </strong>這個功能了
</div>

<div>
  [csharp]<br /> private void InputBoxSample()<br /> {<br /> string Message = Microsoft.VisualBasic.Interaction.InputBox("Welcome to ShareChiWai", "Welcome Messsage", "");<br /> MessageBox.Show("Hi, " + Message, "Welcome");<br /> }<br /> [/csharp]</p>
</div>

<div id="_mcePaste">
  Hope you find it useful
</div>