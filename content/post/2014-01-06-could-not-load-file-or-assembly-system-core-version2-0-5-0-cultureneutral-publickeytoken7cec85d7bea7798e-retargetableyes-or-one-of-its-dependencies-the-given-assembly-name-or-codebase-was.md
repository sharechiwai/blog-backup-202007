---
id: 2983
title: 'Could not load file or assembly &#8216;System.Core, Version=2.0.5.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e, Retargetable=Yes&#8217; or one of its dependencies. The given assembly name or codebase was invalid. (Exception from HRESULT: 0x80131047)'
date: 2014-01-06T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2983
permalink: /2014/01/could-not-load-file-or-assembly-system-core-version2-0-5-0-cultureneutral-publickeytoken7cec85d7bea7798e-retargetableyes-or-one-of-its-dependencies-the-given-assembly-name-or-codebase-was/
categories:
  - ASP.Net Tips and Tricks
tags:
  - IIS
---
今天在Publish 網頁到 **Development Server**時出現以下的錯誤  
&#8220;<span style="color: #ff0000;"><strong>Could not load file or assembly &#8216;System.Core, Version=2.0.5.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e, Retargetable=Yes&#8217; or one of its dependencies. The given assembly name or codebase was invalid. (Exception from HRESULT: 0x80131047)</strong></span>&#8220;

這個是**ASP.Net MVC 3**的網站  
Host 在 **Windows Server 2008 R2** 的 **IIS** 上 安裝了 **.Net Framework 4.0**

在加入了**AutoMapper** 這一個**Nuget Package** 之後便出現這個問題了

做了一會research 之後終於找到解決方法了

**解決方法:**  
大家可以到 以下網址下載及安裝 **.Net 4.5.1**或更新的版本..

<a title="Microsoft .NET Framework 4.5.1 (Offline Installer) for Windows Vista SP2, Windows 7 SP1, Windows 8, Windows Server 2008 SP2 Windows Server 2008 R2 SP1 and Windows Server 2012" href="http://www.microsoft.com/en-gb/download/details.aspx?id=40779" target="_blank">http://www.microsoft.com/en-gb/download/details.aspx?id=40779</a>

這便可以解決這個問題

Hope you find it useful