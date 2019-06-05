---
id: 2892
title: Windows Store App AppBarIcon / AppBar button style images
date: 2013-05-21T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2892
permalink: /2013/05/windows-store-app-appbaricon-appbar-button-style-images/
categories:
  - Windows Store Apps
---
對於像我這些沒有藝術天份的Developer 要在**App**上加**圖**/**Image** 是一個十分難的是  
如果要自己做**AppBarButton** 的**Icon**/**Image** 我相信要完成一個**Windows Store App**的開發會耐要很長很長的時間

幸好在開發**Windows Store App** 上已經有一些已定義好的 **AppBar Icon** / **AppBar button style images** 可以給大家用

這些**AppBarIcon** / **AppBar button style images** 的 **XAML Style** 已經儲存在 **Project**上的**StandardStyles.xaml** 內  
[<img class="alignnone size-full wp-image-2905" alt="Project -> Common Folder -> StandardStyles.xaml" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StandardStyles.png?resize=353%2C169" width="353" height="169" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StandardStyles.png)  
而且分開了十個不同的組別&#8230;  
[<img alt="Windows Store App AppBar Button Image " src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632242.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632242.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632243.png?resize=596%2C258" width="596" height="258" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632243.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632244.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632244.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632245.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632245.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632246.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632246.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632247.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632247.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632248.png?resize=596%2C258" width="596" height="258" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632248.png)

[<img alt="Windows Store App AppBar Button Image " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632249.png?resize=596%2C343" width="596" height="343" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632249.png)

[<img class="alignnone size-full wp-image-2896" alt="Windows Store App AppBar Button Image " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632250.png?resize=596%2C258" width="596" height="258" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632250.png)

[<img class="alignnone size-full wp-image-2897" alt="Windows Store App AppBar Button Image " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632251.png?resize=596%2C258" width="596" height="258" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/IC632251.png)

**E.G.**

大家只需要**Un-comment** 在你的 **Windows Store App Project**內 **Common** 資料夾 上  
**StandardStyles.xaml** 內  
[<img class="alignnone size-full wp-image-2906" alt="StandardStyles.xaml" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StandardStylesCode.png?resize=625%2C226" width="625" height="226" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StandardStylesCode.png)  
你所想用**Button**相關的**Style** 之後在你想用的**AppBarButton**上應用這個**Style** 便可以了

大家可以以圖上的**文字**/**Caption** 找出相對的**XAML Style** 來

**E.G.**

[xml]  
<Button Style="{StaticResource ContactAppBarButton}" Name="AppBarBtnContact" Click="AppBarBtnContact_OnClick" />  
[/xml]

詳情可以參考以下URL  
[http://msdn.microsoft.com/en-us/library/windows/apps/jj841127.aspx](http://msdn.microsoft.com/en-us/library/windows/apps/jj841127.aspx "AppBar button style images")

Hope you find it useful