---
id: 1087
title: 'The &#8216;Microsoft.ACE.OLEDB.12.0&#8217;/&#8217;Microsoft.Jet.OLEDB.4.0&#8217; provider is not registered on the local machine'
date: 2010-12-06T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1087
permalink: /2010/12/the-microsoft-ace-oledb-12-0microsoft-jet-oledb-4-0-provider-is-not-registered-on-the-local-machine/
categories:
  - .Net Tips And Tricks
---
今天嘗試測試能不能使用 **OLEDB** Namespace 來新增Access Database 的Table 時  
Connection String = &#8220;Provider=Microsoft.Jet.OLEDB.4.0; Data Source=D:MyInterestdb1.mdb;&#8221;  
出現了以下的錯誤信息  
&#8220;**<span style="color: #ff0000;">The &#8216;Microsoft.Jet.OLEDB.4.0&#8217; provider is not registered on the local machine</span>**&#8221;

[<img class="alignnone size-full wp-image-1088" title="Provider" src="https://i2.wp.com/farm6.static.flickr.com/5188/5687750217_bdbe9caa0b.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5188/5687750217_bdbe9caa0b.jpg)

&#8220;**<span style="color: #ff0000;">The &#8216;Microsoft.ACE.OLEDB.12.0&#8217; provider is not registered on the local machine</span>**&#8221;  
[<img class="alignnone size-full wp-image-1089" title="Provider" src="https://i0.wp.com/farm6.static.flickr.com/5267/5687750119_9432ce69cb.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5267/5687750119_9432ce69cb.jpg)

原來這是因為這些Provider 不支援 **64 bits Windows** 的關係

**解決方法:**打開你的**Project** 內容 E.G. 雙按 “**My Project**“之後選擇 “**Compile Tab 分頁**“按一下”**Advanced Compile Options**”  
[<img title="CompilerOption" src="https://i0.wp.com/farm6.static.flickr.com/5308/5688335686_a9d57e9b2a.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5308/5688335686_a9d57e9b2a.jpg)在 **Target CPU:** 的選項中選擇“**x86**” 便可  
[<img title="AdvancedCompilerSettings" src="https://i0.wp.com/farm6.static.flickr.com/5026/5687766051_a886cc4974.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5026/5687766051_a886cc4974.jpg)

Hope you find it useful