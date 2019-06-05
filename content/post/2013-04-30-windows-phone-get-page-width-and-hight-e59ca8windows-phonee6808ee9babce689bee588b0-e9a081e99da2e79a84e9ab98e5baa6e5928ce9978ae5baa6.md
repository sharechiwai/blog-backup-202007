---
id: 2827
title: 'Windows Phone Get Page Width and Hight &#8211; 在Windows Phone怎麼找到 頁面的高度和闊度'
date: 2013-04-30T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2827
permalink: '/2013/04/windows-phone-get-page-width-and-hight-%e5%9c%a8windows-phone%e6%80%8e%e9%ba%bc%e6%89%be%e5%88%b0-%e9%a0%81%e9%9d%a2%e7%9a%84%e9%ab%98%e5%ba%a6%e5%92%8c%e9%97%8a%e5%ba%a6/'
categories:
  - Window Phone Development
tags:
  - Windows Phone 8
---
今天又繼續嘗**試Windows Phone** 的開發了..  
做了一個**User Control** 用來做**Popup** 之用的..  
因為**Windows Phone 8** 開始 **Windows Phone** 已經不再是定了一個解析度大小的關係..  
所以在開發時也需要考慮到**Layout** 要應付不同大小解析度的問題

所以便不能 Hard Code 這一個 **User Control**的大小了

原先以為十分容易做到的  
E.G.  
可以使用 <span style="color: #008000;"><strong>LayoutRoot.Height</strong></span>,<span style="color: #008000;"><strong> LayoutRoot.Width</strong></span>  
誰不知..當我使用他們的時候..卻找不到 **Height**和 **Width**

做了一會兒reseach 後終於找到解決方法了

**解決方法**:  
我們可以使用<span style="color: #008000;"><strong>Application.Current.Host.Content</strong> </span>來找出 頁面的屬性

[csharp]  
// 高度 / Height  
double height = Application.Current.Host.Content.ActualHeight  
// 闊度 / Width  
double width = Application.Current.Host.Content.ActualWidth;  
[/csharp]

Hope you find it useful