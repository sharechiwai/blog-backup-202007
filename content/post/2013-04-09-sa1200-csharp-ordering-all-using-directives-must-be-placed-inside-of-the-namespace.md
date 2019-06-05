---
id: 2721
title: 'SA1200 : CSharp.Ordering : All using directives must be placed inside of the namespace.'
date: 2013-04-09T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2721
permalink: /2013/04/sa1200-csharp-ordering-all-using-directives-must-be-placed-inside-of-the-namespace/
categories:
  - StyleCop
tags:
  - StyleCop Warning
---
以下的**StyleCop**警告主要是和**Scope** 有關的..  
&#8220;<span style="color: #ff0000;"><strong>SA1200 : CSharp.Ordering : All using directives must be placed inside of the namespace.</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2730" alt="SA1200 : CSharp.Ordering : All using directives must be placed inside of the namespace" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SA1200.jpg?resize=417%2C58" width="417" height="58" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SA1200.jpg)

當你有很多不同的**Classes** 和**Namespace**  
而你的這個**Class** 和另外一個**Namespace**上的**Class** 有相同的名稱上時..  
把 **directives**放在**Namespace**內會比較好一點..

這個情況有點複雜..有時候再多加解釋

**解決方法:**  
我們只要把**directives**放在**Namespace**內便可以了  
E.G. 把程式碼由這個

[csharp]

<strong>using System;</strong>  
<strong>using System.Collections.Generic;</strong>  
<strong>using System.Linq;</strong>  
<strong>using System.Text;</strong>  
<strong>using System.Threading.Tasks;</strong>

namespace LGetTextWP8.Classes  
{

class Get\_Text\_CL  
{  
}  
}  
[/csharp]

[<img class="alignnone size-full wp-image-2731" alt="SA1200 : CSharp.Ordering : All using directives must be placed inside of the namespace" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/LGetTextWP8_EmptyClass.jpg?resize=368%2C237" width="368" height="237" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/LGetTextWP8_EmptyClass.jpg)  
轉成

[csharp]  
namespace LGetTextWP8.Classes  
{  
<strong> using System;</strong>  
<strong> using System.Collections.Generic;</strong>  
<strong> using System.Linq;</strong>  
<strong> using System.Text;</strong>  
<strong> using System.Threading.Tasks;</strong>

class Get\_Text\_CL  
{  
}  
}

[/csharp]

[<img class="alignnone size-full wp-image-2732" alt="SA1200  CSharp.Ordering  All using directives must be placed inside of the namespace" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Warning6SA1200-CSharp.Ordering-All-using-directives-must-be-placed-inside-of-the-namespace.jpg?resize=339%2C288" width="339" height="288" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/Warning6SA1200-CSharp.Ordering-All-using-directives-must-be-placed-inside-of-the-namespace.jpg)  
Happy Coding &#8211; Please correct me if my concept is wrong