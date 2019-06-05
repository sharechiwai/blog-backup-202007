---
id: 3136
title: 'PowerShell Get Current PowerShell Version Installed- 如何取得已安裝的PowerShell 版本'
date: 2014-04-05T00:00:31+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3136
permalink: '/2014/04/powershell-get-current-powershell-version-%e5%a6%82%e4%bd%95%e5%8f%96%e5%be%97%e7%8f%be%e6%9c%89%e7%9a%84powershell-%e7%89%88%e6%9c%ac/'
categories:
  - Powershell
---
想知道自己正在用那一個版本的**PowerShell**

大家可以用以下的方法來查詢  
我們可以在**PowerShell** 上輸入

<span style="color: #008000;"><strong>$psversiontable<br /> </strong></span>

**PowerShell**的版本可以在 **PSVersion** 的值上找到  
我的**PowerShell**版本是 **Version 3**

<img class="alignnone" src="https://i2.wp.com/farm8.staticflickr.com/7394/14085856401_78b599391f_d.jpg?resize=407%2C201" alt="Get PowerShell Version" width="407" height="201" data-recalc-dims="1" />  
另一個方法是

<span style="color: #008000;"><strong>(get-host).version</strong></span>

或

<span style="color: #008000;"><strong>$PSVersionTable.PSVersion</strong></span>

他們的輸出的結果是一樣的  
<img class="alignnone" src="https://i2.wp.com/farm3.staticflickr.com/2937/14065956916_95edc06da3_d.jpg?resize=500%2C343" alt="Get PowerShell Version" width="500" height="343" data-recalc-dims="1" /> 

Hope you find it useful