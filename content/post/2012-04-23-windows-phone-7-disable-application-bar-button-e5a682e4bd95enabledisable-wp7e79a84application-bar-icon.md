---
id: 2378
title: 'Windows Phone 7 Disable Application Bar button &#8211; 如何Enable/Disable WP7的Application Bar Icon'
date: 2012-04-23T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2378
permalink: '/2012/04/windows-phone-7-disable-application-bar-button-%e5%a6%82%e4%bd%95enabledisable-wp7%e7%9a%84application-bar-icon/'
categories:
  - Window Phone Development
---
在**Windows Phone**中為了能夠令到應用程式更簡潔..  
很多時候都盡量減少使用按鈕..  
而使用**ApplicationBarIconButton** 或 **ApplicationBarContextMenu**等等  
我現在正在寫的程式也是一樣&#8230;  
原來**ApplicationBarIconButton**根**Button** 的處理方法是有點不一樣的

由於程式上有一些功能需要連接到**Web Service**上..  
所以會有小小的**Delay**..  
如果不把**ApplicationBarIconButton** **Disable**的話..  
便用者在等待期間.. 如果心急的話..可能會再次按這個**ApplicationBarIconButton**的按鈕..  
所以便要找放法去**Disable**這個按鈕了&#8230;

一般來說&#8230;因為**ApplicationBarIconButton** 是一個**Button**..  
而他又有一個**IsEnable**的屬性&#8230;  
所以直角給我說: 只要用直接輸入這個**ApplicationBarIconButton**的名稱..  
之後使用**IsEnable**的屬性便可以很簡單地 **Enable**和**Disable**這個**ApplicationBarIconButton**了

[csharp]  
AppBarGetData.IsEnabled=false;  
[/csharp]

誰不知..當我在執行程式的時候..出現了以下的錯誤信息..  
&#8220;<span style="color: #ff0000;"><strong>NullReferenceException</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9aa0a2010c8e47998cdb59ada2d808c4" alt="NullReferenceException" width="736" height="191" /> 

做了一會兒Research之後&#8230;找到了解決方法了.

解決方法:  
原來要參考**ApplicationBarIconButton** 是需要用來 **ApplicationBar.Buttons[]** 這個屬性的  
其中我們要在**Button[]**中輸入我們想參考的**ApplicationBarIconButton**的**位置**/**Index**  
是由**ApplicationBar**上的左至右排列的  
**ApplicationBar**最左邊的**ApplicationBarIconButton**的**Index/位置**是 &#8220;0&#8221;&#8230;  
我們可以以這個方法..找出**ApplicationBarIconButton**的參考..之後修改他的屬性  
E.G.

[csharp]  
//或出這個ApplicationBarIconButton 之後Assign他到其中一個Variable備用  
ApplicationBarIconButton AppBarButton1 = (ApplicationBarIconButton)ApplicationBar.Buttons[0];  
//設定這個ApplicationBarIconButton的屬性  
AppBarButton1.IsEnabled = IsEnable;  
//另一個做法是直接Cast這個成ApplicationBarIconButton/ApplicationBarMenuButton  
((ApplicationBarIconButton)ApplicationBar.Buttons[1]).IsEnabled = IsEnable;  
[/csharp]

Hope you find it useful