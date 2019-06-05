---
id: 1844
title: '.Net CheckBox State between Checked and UnChecked &#8211; 怎樣設定CheckBox 狀態成Checked 和 Unchecked中間'
date: 2011-07-05T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1844
permalink: '/2011/07/net-checkbox-state-between-checked-and-unchecked-%e6%80%8e%e6%a8%a3%e8%a8%ad%e5%ae%9acheckbox-%e7%8b%80%e6%85%8b%e6%88%90checked-%e5%92%8c-unchecked%e4%b8%ad%e9%96%93/'
categories:
  - .Net Tips And Tricks
tags:
  - visual studio
---
今日有朋友問了一個很好的問題&#8230;  
怎樣可以做到一個和其他軟件公司一樣的**Checkbox&#8230;不是Check和 uncheck狀態**的  
例如..在很多軟體在安裝他們的元件時也會有這樣的效果  
在**Checked** 和 **Unchecked**的狀態中間 的不定狀態  
[<img class="alignnone" title="Checkbox Indetermine state" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c3513025eb8f4ce5a240eb96619ad466/renditions/fullsize.jpg?resize=429%2C379" alt="" width="429" height="379" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c3513025eb8f4ce5a240eb96619ad466/renditions/fullsize.jpg)

經過一會兒的研究終於明了不同的**CheckBox**狀態了

**解決方法**:  
原來**CheckBox** 控件上有一個 &#8220;**CheckState/檢查狀態**&#8221; 的屬性  
入面有三個不同的狀態  
**Checked** &#8211; 己檢查  
**UnChecked** &#8211; 未檢查  
**Indeterminate** &#8211; 不定

[<img class="alignnone" title="CheckBox State" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05e831b6f52e4e00ba28858f9de61ac7/renditions/fullsize.jpg?resize=243%2C121" alt="" width="243" height="121" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05e831b6f52e4e00ba28858f9de61ac7/renditions/fullsize.jpg)

只是把&#8221;**CheckState/檢查狀態**&#8221; 的屬性變成 &#8220;**Indeterminate/不定**&#8220;便可以做到這個效果

我們亦都可以使用程式碼來實行這個效果  
**VB.Net**

[vb]  
cb_ShareChiWaiSample.CheckState = CheckState.Indeterminate  
[/vb]

**C#**

[csharp]  
cb_ShareChiWaiSample.CheckState = CheckState.Indeterminate;  
[/csharp]

Hope you find it useful