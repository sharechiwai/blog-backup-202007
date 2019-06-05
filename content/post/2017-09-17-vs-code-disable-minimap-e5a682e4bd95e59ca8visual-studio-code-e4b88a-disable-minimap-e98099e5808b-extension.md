---
id: 4029
title: 'VS Code disable minimap &#8211; 如何在Visual Studio Code 上 Disable Minimap 這個 extension'
date: 2017-09-17T15:39:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4029
permalink: '/2017/09/vs-code-disable-minimap-%e5%a6%82%e4%bd%95%e5%9c%a8visual-studio-code-%e4%b8%8a-disable-minimap-%e9%80%99%e5%80%8b-extension/'
categories:
  - Visual Studio
tags:
  - Plugin
  - Visual Studio Code
  - VSCode
  - VSCode Plugin
---
解決方法十分簡單:  
我們可以去 &#8220;**File**&#8221; -> &#8220;**Preferences**&#8221; -> &#8220;Settings&#8221;  
的 &#8220;**User Settings**&#8221; 上把 &#8220;<span style="color: #008000;"><strong>editor.minimap.</strong>enabled</span>&#8221; 設定為 <span style="color: #ff0000;"><strong>false</strong></span> 便可以了

<pre>"editor.minimap.enabled": false,
</pre>

[<img class="alignnone size-large wp-image-4031" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif?resize=625%2C515" alt="Disable minimap" width="625" height="515" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif?resize=1024%2C843 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif?resize=300%2C247 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif?resize=768%2C632 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif?resize=624%2C514 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/09/disable-minimap.gif)  
Hope you find it useful