---
id: 1842
title: 'Date and Time picker how to allow user to pick time as well &#8211; 如果令到 .Net的日期與時間選擇器 可以選擇時間?'
date: 2011-07-02T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1842
permalink: '/2011/07/date-and-time-picker-how-to-allow-user-to-pick-time-as-well-%e5%a6%82%e6%9e%9c%e4%bb%a4%e5%88%b0-net%e7%9a%84%e6%97%a5%e6%9c%9f%e8%88%87%e6%99%82%e9%96%93%e9%81%b8%e6%93%87%e5%99%a8-%e5%8f%af/'
categories:
  - .Net Tips And Tricks
tags:
  - visual studio
  - WinForm
---
今日朋友又問了一個很好的問題..  
在&#8221;**Window Form / WPF**&#8221; 中的 &#8220;**Date Time Picker/日期時間選擇器&#8221;**怎樣才可以自行選擇時間?  
通常當我們把&#8221;**Date Time Picker**&#8221; 放進了我們的程式上..  
多數只會看到日期的  
[<img class="alignnone" title="Date Time Picker Sample" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7312b0ca147144a397ec302930692658/renditions/fullsize.jpg?resize=298%2C231" alt="" width="298" height="231" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7312b0ca147144a397ec302930692658/renditions/fullsize.jpg)

但是他名叫&#8221;**Date Time Picker**&#8220;..  
那麼我們便應該可以選擇時間呢..

解決方法十分簡單..  
我們只要選擇 這一個**Date Time Picker控件**  
在&#8221;屬性視窗&#8221;上修改 &#8220;**Format/格式**&#8220;屬性 為&#8221;**Custom/自定**&#8221;  
之後在&#8221;**CustomFormat**/**自定格式**&#8220;屬性上輸入自己想要的 格式便可..  
如: <span style="color: #339966;"><strong>yyyy/MM/d hh:mm:ss</strong></span>  
[<img class="alignnone" title="Date Time Picker Custom Format" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/95a551faa58447f18080b7cb97735b2e/renditions/fullsize.jpg?resize=326%2C290" alt="" width="326" height="290" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/95a551faa58447f18080b7cb97735b2e/renditions/fullsize.jpg)  
這會顯示 &#8220;<span style="color: #339966;"><strong>2011 6月 25 02:03:05</strong></span>&#8221;

在這裡我們亦都可以更變 選擇後日期與時間的顯示格式&#8230;

&#8220;**CustomFormat/自定格式**&#8221; 屬性 是會在 &#8220;**Format/格式**&#8220;屬性 選擇了為&#8221;**Custom/自定**&#8221;  
才會被應用的  
[<img class="alignnone" title="DateTimePicket CustomFormat" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/468eab0efb2541e8bfd91b927e40289c/renditions/fullsize.jpg?resize=289%2C128" alt="" width="289" height="128" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/468eab0efb2541e8bfd91b927e40289c/renditions/fullsize.jpg)

**DateTimePicker&#8221;Format/格式&#8221;屬性** 還有以下4種格式可以給大家選擇  
**Long** &#8211; 會顯示日子的全寫  
**Short** &#8211; 日子簡寫  
**Time** &#8211; 只會顯示時間  
**Custom** &#8211; 會選用自定的格式

Hope you find it useful