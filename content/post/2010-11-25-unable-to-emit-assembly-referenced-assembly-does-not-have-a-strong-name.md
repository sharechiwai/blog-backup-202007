---
id: 1043
title: 'Unable to emit assembly: Referenced assembly does not have a strong name'
date: 2010-11-25T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1043
permalink: /2010/11/unable-to-emit-assembly-referenced-assembly-does-not-have-a-strong-name/
categories:
  - .Net Tips And Tricks
---
今天嘗試更新自己寫的一個**Project** 時..  
[因為最近公司有個新朋友加入&#8230; 介紹了很多新方法..改善了很多以前Development 時做得不好的地方] <&#8211; 謝謝你  
在更新這個**Project** 時&#8230;以前有用開一個自己寫給公司用的 **Library** [其實和[**ShareChiWaiLib**](http://sharechiwailib.codeplex.com/) 差不多的], 以前是把這個Library 放在**Network Drive/找複製貼上到Project Folder** 上 之後用**Add Reference** 方式來把這個Library 加入Project 上..  
現在的方法比較好一點的..就是**Add Project Reference** 方式&#8230; 每當這個Library 有更新時[**Feature Update/ Bug Fix**]&#8230;只要recompile這個Project 便會得到最新的Library DLL 了  
這個方法已經在好幾個Project 上運用..效果很好&#8230;很方便

但當我在這個Project 上使用這個**Project Reference** 中的Library 時 出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Unable to emit assembly: Referenced assembly &#8216;xxx&#8217; does not have a strong name</strong></span>&#8221;  
[<img title="EmitAssemblyReferencedAssembly" src="https://i2.wp.com/farm6.static.flickr.com/5283/5687768423_14f98f6301.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5283/5687768423_14f98f6301.jpg)

這是..我在想&#8230;這個是**Project Reference** &#8230;怎樣才可以 把這個**DLL Sign 成Strong Name** 的**Reference** 呢&#8230; 網上的解決放法都是有一個**DLL** 之後用**Command Prompt** 來Sign 這個**Reference**&#8230;但是這跟我的情況很像不相同&#8230;

最後終於找到解決方法了..  
**解決方法:**  
1) 打開這個Project 的 &#8220;**Properties/內容**&#8221;  
2) 選擇 &#8220;**Signing tab/簽署分頁**&#8221;  
[<img title="Signing" src="https://i2.wp.com/farm6.static.flickr.com/5247/5687827871_68fdefb952.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5247/5687827871_68fdefb952.jpg)  
3) 選取&#8221;**Sign the assembly**&#8220;->之後在&#8221;**Choose a strong name key file**&#8221; 上選擇 &#8220;**<New&#8230;>**&#8221;  
之後填上這個**Key file name** 和輸入密碼便可[如果你希望用密碼來保護這個 **Strong Name Key的話**]

[<img class="alignnone size-full wp-image-1045" title="CreateStrongNameKey" src="https://i2.wp.com/farm6.static.flickr.com/5250/5687859317_04f8b8ec34.jpg?w=625" alt="CreateStrongNameKey" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5250/5687859317_04f8b8ec34.jpg)

Hope you find it useful