---
id: 3722
title: 'ASP.Net MVC add Currency Sign on Razor &#8211; 如何在ASP.Net MVC 上那些和貨幣相關的 field 加上貨幣符號呢?'
date: 2016-08-05T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3722
permalink: '/2016/08/asp-net-mvc-add-currency-sign-on-razor-%e5%a6%82%e4%bd%95%e5%9c%a8asp-net-mvc-%e4%b8%8a%e9%82%a3%e4%ba%9b%e5%92%8c%e8%b2%a8%e5%b9%a3%e7%9b%b8%e9%97%9c%e7%9a%84-field-%e5%8a%a0%e4%b8%8a%e8%b2%a8/'
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC
  - Data Annotation
  - Razor
---
最近的**Freelance Project** 終於去到埋尾階段  
現在主要是解決一些小小的**UI** / **UX** 問題  
第一個問題就是如何在**Razor** 上那些和貨幣相關的 field 加上貨幣符號呢?

**ASP.Net MVC** 的**Data Annotation** 令這個有時都幾麻煩的事情簡單很多

我們只需要在**Model**上的**貨幣field** 加上以下的**Data annotation**便可以了  
不用自行在**cshtml**上加上貨幣符號 String.Format這些東西  
<img class="alignnone size-medium wp-image-3723" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency.png?resize=300%2C64" alt="ASP.Net MVC Currency Sign by Using Data Annotation" width="300" height="64" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency.png?resize=300%2C64 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency.png?resize=624%2C133 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency.png?w=656 656w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /> 

E.G.

<pre>[DisplayFormat(DataFormatString = "{0:C}", ApplyFormatInEditMode = true)]
        [DisplayName("Amount")]
        public decimal Amount { get; set; }

        [DisplayFormat(DataFormatString = "{0:C}", ApplyFormatInEditMode = true)]
        public decimal AmountRemaining { get; set; }
</pre>

在**Model** 上加了這個**Data Annotation**之後在那個地方使用言個field的時候都會自動加上**貨幣符號**了.  
[<img class="alignnone size-medium wp-image-3724" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency2.png?resize=300%2C88" alt="ASP.Net MVC Currency Sign via Data Annotation" width="300" height="88" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency2.png?resize=300%2C88 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency2.png?w=545 545w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/aspnetcurrency2.png)

Hope you find it useful