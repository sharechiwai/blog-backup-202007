---
id: 2738
title: 'SA1633 : CSharp.Documentation : The file has no header, the header Xml is invalid, or the header is not located at the top of the file.'
date: 2013-04-11T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2738
permalink: /2013/04/sa1633-csharp-documentation-the-file-has-no-header-the-header-xml-is-invalid-or-the-header-is-not-located-at-the-top-of-the-file/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
&#8220;<span style="color: #ff0000;"><strong>SA1633 : CSharp.Documentation : The file has no header, the header Xml is invalid, or the header is not located at the top of the file</strong></span>.&#8221;  
[<img class="alignnone size-full wp-image-2740" alt="SA1633 : CSharp.Documentation : The file has no header, the header Xml is invalid, or the header is not located at the top of the file." src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1633.png?resize=480%2C68" width="480" height="68" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1633.png)

**StyleCop** 有些守則是要每一個文件上的開首  
都要有一段**XML**碼去簡單說明這個程式碼或文件是用來做什麼..  
版權是誰的等等

[csharp]  
//&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;  
// <copyright file="Get\_Text\_CL.cs" company="LookFor.HK">  
// Copyright LookFor.HK. All rights reserved.  
// </copyright>  
//&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;  
[/csharp]

[<img alt="SA1633 : CSharp.Documentation : The file has no header, the header Xml is invalid, or the header is not located at the top of the file." src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1633Fix_DocumentHeader.jpg?resize=491%2C315" width="491" height="315" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1633Fix_DocumentHeader.jpg)

Happy Coding