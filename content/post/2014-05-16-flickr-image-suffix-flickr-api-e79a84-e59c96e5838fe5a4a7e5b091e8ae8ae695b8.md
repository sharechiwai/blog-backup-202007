---
id: 3184
title: 'Flickr Image Suffix &#8211; Flickr API 的 圖像大少變數'
date: 2014-05-16T00:00:43+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3184
permalink: '/2014/05/flickr-image-suffix-flickr-api-%e7%9a%84-%e5%9c%96%e5%83%8f%e5%a4%a7%e5%b0%91%e8%ae%8a%e6%95%b8/'
categories:
  - Flickr
tags:
  - Flickr API
---
最近開始研究 **Flickr API**..  
常常忘記他們大小的變數  
如果把變數設定錯誤便會出現以下的情況..  
&#8220;<span style="color: #ff0000;"><strong>This image or video is currently unavailable</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2900/14203284979_0c8b220ce8_z.jpg?resize=564%2C423" alt="Flickr - This image or video is currently unavailable" width="564" height="423" data-recalc-dims="1" /> 

所以便記下來方便自己了

  * **s** &#8211; small square 75&#215;75
  * **q** &#8211; large square 150&#215;150
  * **t** &#8211; thumbnail, 100 on longest side
  * **m** &#8211; small, 240 on longest side
  * **n** &#8211; small, 320 on longest side
  * **&#8211;**  &#8211; medium, 500 on longest side
  * **z** &#8211; medium 640, 640 on longest side
  * **c** &#8211; medium 800, 800 on longest side†
  * **b** &#8211; large, 1024 on longest side*
  * **o** &#8211; original image, either a jpg, gif or png, depending on source format

詳情可以參考以下的網頁  
<a title="Flickr API - Image Suffic" href="https://www.flickr.com/services/api/misc.urls.html" target="_blank">https://www.flickr.com/services/api/misc.urls.html</a>

Hope you find it useful