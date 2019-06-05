---
id: 2719
title: 'SA1300 : CSharp.Naming : namespace names begin with an upper-case letter &#8211; StyleCop Warning'
date: 2013-04-08T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2719
permalink: /2013/04/sa1300-csharp-naming-namespace-names-begin-with-an-upper-case-letter-stylecop-warning/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
&#8220;<span style="color: #ff0000;"><strong>SA1300 : CSharp.Naming : namespace names begin with an upper-case letter</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2726" alt="SA1300 : CSharp.Naming : namespace names begin with an upper-case letter" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SA1300-namespace-names-begin-with-an-upper-case-letter.jpg?resize=420%2C53" width="420" height="53" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SA1300-namespace-names-begin-with-an-upper-case-letter.jpg)

這個警告是因為我把用來放入自定**Helper Clas**s的資料夾用了小寫 來開頭  
之後在入面建立的**Class** 的 **Namespace** 便會用了小寫 來定義..

[csharp]  
namespace LGetTextWP8.<strong>classes</strong>{

}  
[/csharp]

**解決方法**十分簡單  
只要把資料夾的開首的一個字母轉成大寫便可以了  
[<img class="alignnone size-full wp-image-2727" alt="SA1300 : CSharp.Naming : namespace names begin with an upper-case letter - Updated Folder" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/LowerClassFolder.jpg?resize=242%2C224" width="242" height="224" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/LowerClassFolder.jpg)

[當然你也是把你的**Namespace** 也轉成首個字母大寫]

[csharp]  
namespace LGetTextWP8.<strong>Classes</strong>{

}  
[/csharp]

Happy Coding