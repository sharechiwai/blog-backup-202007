---
id: 2632
title: 'StyleCop &#8211;  SA1001: CSharp.Spacing: Invalid spacing around the comma.'
date: 2013-01-02T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2632
permalink: /2013/01/stylecop-sa1001-csharp-spacing-invalid-spacing-around-the-comma/
categories:
  - StyleCop
---
今天開始更新我之前寫的**ShareChiWaiUtilityLib**的程式碼..  
希望從現在開始我寫的程式碼會比較有質數一點  
使用**StyleCop**的方法十分簡單 只要在**Visual Studio** 的Solution Explorer上的Source Code 檔案上按右鍵, 選擇 &#8220;**Run StyleCop**&#8221;  
<a href="http://s1255.beta.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/SA1600ClassMustHaveaDocumentHeader.jpg.html" target="_blank"><img alt=" photo SA1600ClassMustHaveaDocumentHeader.jpg" src="https://i2.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/SA1600ClassMustHaveaDocumentHeader.jpg?w=625" border="0" data-recalc-dims="1" /></a>  
之後 結果便會在 **Output Windows** 的 &#8220;**Error List**&#8221; Windows 上的Warning 分頁 上出現

當我執行**StyleCop**的時候..  
第一個收到的Warning是1 &#8220;<span style="color: #ff0000;"><strong>SA1001: CSharp.Spacing: Invalid spacing around the comma.</strong></span>&#8221;  
<a href="http://s1255.beta.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/SA1001InvalidSpacingAroundComma.png.html" target="_blank"><img alt=" photo SA1001InvalidSpacingAroundComma.png" src="https://i2.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/SA1001InvalidSpacingAroundComma.png?w=625" border="0" data-recalc-dims="1" /></a>

問題是因為我的程式碼上在**分號/Comma**後沒有留一個空格  
<span style="color: #008000;"><strong>tbl.Rows.Add(new Object[] { &#8220;00005&#8221;,&#8221;Beef&#8221;,1.99,0.8,&#8221;00002&#8243; });</strong></span>  
<a href="http://s1255.beta.photobucket.com/user/sharechiwai/media/Tech%20Blog%202013/SA1001InvalidSpacingAroundCommaCode.png.html" target="_blank"><img alt=" photo SA1001InvalidSpacingAroundCommaCode.png" src="https://i0.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Tech%20Blog%202013/SA1001InvalidSpacingAroundCommaCode.png?w=625" border="0" data-recalc-dims="1" /></a>  
**解決方法**:  
只要在分號後加上空格便可以了  
**tbl.Rows.Add(new Object[] { &#8220;00006&#8221;, &#8220;Broccoli&#8221;, 1.09, 0.5, &#8220;00003&#8221; });**

Happy Coding =P