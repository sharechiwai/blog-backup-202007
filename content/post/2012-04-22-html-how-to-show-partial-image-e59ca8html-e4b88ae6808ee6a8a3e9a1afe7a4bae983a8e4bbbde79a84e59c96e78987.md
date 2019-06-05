---
id: 2374
title: 'HTML How to show partial Image &#8211; 在HTML 上怎樣顯示部份的圖片'
date: 2012-04-22T00:01:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2374
permalink: '/2012/04/html-how-to-show-partial-image-%e5%9c%a8html-%e4%b8%8a%e6%80%8e%e6%a8%a3%e9%a1%af%e7%a4%ba%e9%83%a8%e4%bb%bd%e7%9a%84%e5%9c%96%e7%89%87/'
categories:
  - HTML/CSS
---
今天需要在網頁上做一些圖像處理的功能&#8230;  
第一個難是..  
怎樣可以在網頁上只顯示一個**JPG**/**PNG**/**GIF**的圖片..  
的其中一部份&#8230;  
E.G.  
右上角

嘗試過在Div上設定**Max-Width** 和**Max-Height**都不能成功  
如果在圖片上使用Width/Height的屬性的話..  
這只會改變圖片的大小的  
最後終於找到解決方法了  
解決方法:  
我們可以使用 **overflow:hidden** 來解決

E.G.

[html]</pre>  
<div style="width: 200px; height: 200px; overflow: hidden;"><img src="http://i1255.photobucket.com/albums/hh631/sharechiwai/Travel%202012/Borough%20Market%20London/WP_003652.jpg" alt="" /></div>  
<pre>  
[/html]

另一個方法是在**img tag**上使用**css**中的**Clip**的屬性

[html]  
<img style="clip: rect(0px,200px,200px,0px);" src="http://i1255.photobucket.com/albums/hh631/sharechiwai/Travel%202012/Borough%20Market%20London/WP_003652.jpg" alt="" />  
(top/上, right/右, bottom/下, left/左)  
[/html]

用**css**中**clip**的好處是..可以設定顯然的地方  
E.G.  
<img style="clip: rect(200px,200px,200px,0px);" src="https://i1.wp.com/i1255.photobucket.com/albums/hh631/sharechiwai/Travel%202012/Borough%20Market%20London/WP_003652.jpg?w=625" alt="" data-recalc-dims="1" />  
Hope you find it useful