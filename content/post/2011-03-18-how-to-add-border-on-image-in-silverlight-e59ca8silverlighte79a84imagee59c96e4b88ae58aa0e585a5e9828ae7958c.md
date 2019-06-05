---
id: 1669
title: 'How to Add border on Image in Silverlight &#8211; 在Silverlight的Image圖上加入邊界'
date: 2011-03-18T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1669
permalink: '/2011/03/how-to-add-border-on-image-in-silverlight-%e5%9c%a8silverlight%e7%9a%84image%e5%9c%96%e4%b8%8a%e5%8a%a0%e5%85%a5%e9%82%8a%e7%95%8c/'
categories:
  - Silverlight Tips and Tricks
---
最近開始有更多的機會接觸**Silverlight**了  
發現在設計時出現有小小的煩惱..  
就是**Image Control** 放到在**Canvas**時  
由於**Image**沒有**Border**的在**Expression Blend** 的 **Design Mode** 中是看不到的

所以如果要在**Expression Blend**上 **Layout**有用**Image Control**的 地方時..  
會有些困難..

**解決方法:**  
由於**Image**沒有**Border**的關係..  
所以我們可以自行加入一個**Border Control**用來包圍這個**Image**..  
之後把**Image**的**Margin**設定成0..Image便可以用這個Border Control的會部面積了  
E.G.

<Border BorderThickness=&#8221;1,1,1,1&#8243; BorderBrush=&#8221;#FF000000&#8243; >  
<Image x:Name=&#8221;Img_1&#8243; Visibility=&#8221;Visible&#8221; Height=&#8221;200&#8243; Width=&#8221;200&#8243; />  
</Border>  
或者可以使用Expression Blend來做這個動作  
可以 Right Click 這個Image Control.之後選擇&#8221;Group Into&#8221; ->&#8221;Border&#8221;  
之後設定Image 的Margin 為0 和設定Border 的colour便可

Hope you find it useful