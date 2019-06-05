---
id: 2746
title: 'SA1400 : CSharp.Maintainability : The class must have an access modifier.'
date: 2013-04-13T00:00:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2746
permalink: /2013/04/sa1400-csharp-maintainability-the-class-must-have-an-access-modifier/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
今天另一個要處理的**StyleCop** 警告是  
&#8220;<span style="color: #ff0000;"><strong>SA1400 : CSharp.Maintainability : The class must have an access modifier.</strong></span>&#8221;

[<img class="alignnone size-full wp-image-2747" alt="SA1400 : CSharp.Maintainability : The class must have an access modifier." src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1400.jpg?resize=375%2C152" width="375" height="152" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1400.jpg)

&nbsp;

原來在原本的Class Template 是沒有定義 Access Modifier的

[<img class="alignnone size-full wp-image-2748" alt="SA1400 : CSharp.Maintainability : The class must have an access modifier." src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1400Isue.jpg?resize=421%2C115" width="421" height="115" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1400Isue.jpg)

[csharp]  
<strong>class Get\_Text\_CL</strong>  
{  
}  
[/csharp]

**解決方法**  
只要在**Class**的開頭加上適當的 **Access Modifer** 便可以了  
E.G. **Public**, **Protected**, **Private**..等等

E.G.

[csharp]  
<strong>public class Get\_Text\_CL</strong>  
{  
}  
[/csharp]

終於解決了 所有的警告..  
[<img class="alignnone size-full wp-image-2749" alt="StyleCop All Fixed" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopAllFixed.jpg?resize=413%2C192" width="413" height="192" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopAllFixed.jpg)  
Happy Coding