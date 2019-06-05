---
id: 2763
title: 'windows phone button text wrap &#8211; Windows Phone 按鈕Button Content Word Wrap'
date: 2013-04-17T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2763
permalink: '/2013/04/windows-phone-button-text-wrap-windows-phone-%e6%8c%89%e9%88%95button-content-word-wrap/'
categories:
  - Window Phone Development
tags:
  - XAML
---
今天在更新<a title="LGetText Windows Phone" href="http://www.windowsphone.com/en-gb/store/app/lgettext/232b64c7-43e6-4510-9aad-9e341a20a575" target="_blank"><strong>LGetText</strong></a>時  
在使用的&#8221;**按鈕** / **Button**&#8221; 的字體太小了&#8230;  
比較不好看.. 但是當我把字增大後  
在按鈕上的字因為按鈕的大小而有些被遮住了  
[<img alt="Windows Phone Button Text Too Long - Before Word Wrap" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/BeforeWordWrapButton.png?resize=469%2C519" width="469" height="519" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/BeforeWordWrapButton.png)

E.G.  
我用的**XAML** 程式碼是這樣的 用了一個 **Button Tag**

[html]

<Button x:Name="btnSpeechToText" HorizontalAlignment="Left" Margin="10,30,0,0" VerticalAlignment="Top" Height="480" Width="436" Text="Press to Say something" FontSize="36" FontFamily="Segoe WP Black"/>  
[/html]

做了一會兒research之後發現解決方法十分簡單

**解決方法**:  
原來只需要在**Button** 內 加入一個 **TextBlock** 便可以使用**TextBlock**的 **TextWrapping**

[html]  
<Button x:Name="btnSpeechToText" HorizontalAlignment="Left" Margin="10,30,0,0" VerticalAlignment="Top" Height="480" Width="436" Click="BtnSpeechToText_OnClick" BorderBrush="{StaticResource TransparentBrush}" >  
<TextBlock TextWrapping="Wrap" x:Name="txtSpeechToText" d:LayoutOverrides="VerticalAlignment" Text="Press to Say something" FontSize="36" FontFamily="Segoe WP Black"/>  
</Button>  
[/html]

[<img class="alignnone size-full wp-image-2765" alt="Windows Phone Button Word Wrap" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WordWrapButton.png?resize=483%2C482" width="483" height="482" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WordWrapButton.png)

Hope you find it useful