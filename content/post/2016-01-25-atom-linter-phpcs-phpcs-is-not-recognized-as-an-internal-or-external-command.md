---
id: 3559
title: 'Atom Linter-PHPCS &#8211; &#8216;phpcs&#8217; is not recognized as an internal or external command'
date: 2016-01-25T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3559
permalink: /2016/01/atom-linter-phpcs-phpcs-is-not-recognized-as-an-internal-or-external-command/
categories:
  - Atom
tags:
  - Atom
  - Atom Plugins
  - Composer
  - Package Manager
---
今日使用**Atom** 來寫 **PHP code**是出現以下錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>&#8216;phpcs&#8217; is not recognized as an internal or external command</strong></span>&#8221;

**Linter-PHPCS** 是**Atom Editor**的一個 用來檢查 P**HP Coding Standard** 的P**l**ugin  
就像**.Net**中的**StyleCop** 差不多  
今日在使用時出現了這個問題  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1681/24454716040_959080c5c4_z.jpg?resize=625%2C399" alt="Error 'PHPCS' is not recognized as an internal or External Command" width="625" height="399" data-recalc-dims="1" /> 

**解決方法**十分簡單  
大家可以在**Atom**的 **Setting**->**Packages** tab上找出 **Linter-phpcs** package  
之後在**Settings**/ **設定**上輸入 **PHPCS** 的 **executable path**便可以了  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1681/24632439122_f3818ff932_z.jpg?resize=625%2C455" alt="Linter-PHPCS Execution Path" width="625" height="455" data-recalc-dims="1" /> 

Happy Coding