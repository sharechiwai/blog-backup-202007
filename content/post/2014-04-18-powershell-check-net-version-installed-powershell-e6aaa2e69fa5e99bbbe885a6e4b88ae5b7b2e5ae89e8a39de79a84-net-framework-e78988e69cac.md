---
id: 3143
title: 'Powershell check .Net Version installed &#8211; PowerShell 檢查電腦上已安裝的 .Net Framework 版本'
date: 2014-04-18T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3143
permalink: '/2014/04/powershell-check-net-version-installed-powershell-%e6%aa%a2%e6%9f%a5%e9%9b%bb%e8%85%a6%e4%b8%8a%e5%b7%b2%e5%ae%89%e8%a3%9d%e7%9a%84-net-framework-%e7%89%88%e6%9c%ac/'
categories:
  - Powershell
---
**PowerShell** 檢查電腦上已安裝的 **.Net Framework** 版本

我們可以輸入  
<span style="color: rgb(0, 128, 0);"><strong>[environment]::Version</strong></span>  
他會轉出 **.Net Framework**的 **Major**, **Minor**, **Build**, **Revision** 等的版本資訊  
**E.G.**  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7426/13938773767_d62d39529c_z.jpg?resize=625%2C171" alt="Powershell Get Installed .Net Framework Version " width="625" height="171" data-recalc-dims="1" />  
**.Net Version 4**

或者大家可以執行以下指令 也可以找到電腦上已安裝的 **.Net Framework** 版本  
<span style="color: rgb(0, 128, 0);"><strong>[System.Runtime.InteropServices.RuntimeEnvironment]::GetSystemVersion()</strong></span>

<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5338/13938817668_7fc07891b5_z.jpg?resize=625%2C57" alt="Powershell Get .Net Framework Version GetSystemVersion()" width="625" height="57" data-recalc-dims="1" /> 

Hope you find it useful