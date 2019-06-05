---
id: 3114
title: Crystal Report Show page footer on first page only
date: 2014-03-26T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3114
permalink: /2014/03/crystal-report-show-page-footer-on-first-page-only/
categories:
  - Crystal Report Tips and Tricks
---
今天要更新公司客戶的一個報告..  
這個報告是用**Crystal Report XI R2** 寫的..  
客戶想在**Report**首頁的**Footer**上加入他們的公司地址等的一些文字

由於只是需要方在首頁的**Page Footer**上  
所以解決方法也不太複雜

我們可以使用**Section Expert** 中的**Suppress** 再加一個簡單的**Formula**便可以解決

**解決方法**  
在**Crystal Report**的**Design Mode**上 的邊邊上按右鍵..  
之後選擇&#8221;**Section Expert&#8230;**&#8221;  
<img class="alignnone" alt="Crystal Report Section Expert..." src="https://i1.wp.com/farm8.staticflickr.com/7018/13580702885_5b39ba0dc6_d.jpg?resize=286%2C283" width="286" height="283" data-recalc-dims="1" />  
&#8220;**Section Expert**&#8221; Windows 便會彈出來  
之後我們可以在&#8221;**Sections:**&#8221; 區域上選擇 &#8220;**Page Footer**&#8221; &#8211; 因為我們希望把資料/文字只顯示在 第一頁上  
在右邊&#8221;**Common tab**&#8221; 入 按一下 &#8220;**Suppress (No Drill-Down)**&#8220;右方的 &#8220;**Formula**&#8221; 按鈕  
在&#8221;**Formula Editor &#8211; Suppress(No Drill Down)**&#8221; Window上輪入 以下**Formula**

[xml]  
PageNumber >1  
[/xml]

<img class="alignnone" alt="Crystal Report Section Expert Formula to show on First page footer only" src="https://i2.wp.com/farm4.staticflickr.com/3737/13580702835_ea012ccd38_d.jpg?resize=500%2C452" width="500" height="452" data-recalc-dims="1" />  
這個意思是當**Page Number**大過**1**便**Suppress** 隱藏這個 **Page Footer**

Hope you find it useful