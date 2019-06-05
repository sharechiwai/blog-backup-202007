---
id: 2887
title: 'How to create Rate this app button on Windows Phone App &#8211; 在Windows Phone App 上怎樣連結到評級與反饋的功能'
date: 2013-05-20T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2887
permalink: '/2013/05/how-to-create-rate-this-app-button-on-windows-phone-app-%e5%9c%a8windows-phone-app-%e4%b8%8a%e6%80%8e%e6%a8%a3%e9%80%a3%e7%b5%90%e5%88%b0%e8%a9%95%e7%b4%9a%e8%88%87%e5%8f%8d%e9%a5%8b%e7%9a%84/'
categories:
  - Window Phone Development
---
我相信**Apps**越多 好 **Review** 便會有更多人**Download**你的Apps  
既使用差的Review 也可以增加改善這個App的提議 / Idea  
令你的**App** 更加好

那麼如何在**Windows Phone App** 上加入一個給使用都在**Windows Phone MarketPlace**上 **評分**/**Rate**你的**App** 的功能呢?

解決方法十分簡單  
我們可以使用 **MarketplaceReviewTask** 來實行

**解決方法**

[csharp]

MarketplaceReviewTask marketplaceReviewTask = new MarketplaceReviewTask();

marketplaceReviewTask.Show();

[/csharp]

[<img class="alignnone size-full wp-image-2888" alt="LGetText Rate and Review Image" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/wp_ss_20130918_0001.png?resize=480%2C800" width="480" height="800" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/wp_ss_20130918_0001.png)

Hope you find it useful