---
id: 3248
title: 'Excel remove tfs connection &#8211; 如何移除在Excel 上的 TFS Connection'
date: 2014-06-25T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3248
permalink: '/2014/06/excel-remove-tfs-connection-%e5%a6%82%e4%bd%95%e7%a7%bb%e9%99%a4%e5%9c%a8excel-%e4%b8%8a%e7%9a%84-tfs-connection/'
categories:
  - Team Foundation Server
tags:
  - Excel
  - TFS
---
今天朋友因為要用**TFS** 來**Export** 一個我們現有**Project**的**Task List**給老闆

因為在**TFS Export**做**Excel**檔案時..他會幫你自動連接**TFS**..當修改完這個Excel後按儲存..  
他便會更新到**TFS Server**上 [這個功能各有各好..]

為了不被老闆修改或放**Comment** 影響我們的**TFS Work Item**所以便要移除在**Excel** 上的 **TFS Connection**  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2904/14791298474_16cf0a11dd_z.jpg?resize=625%2C261" alt="TFS work item in Excel format with TFS connection" width="625" height="261" data-recalc-dims="1" /> 

那麼如**何移除在Excel 上的 TFS Connection**?

在**Excel**上 的 &#8220;**Design** / **設計** **Ribbon**&#8221; 選擇 &#8220;**Convert Table to Range** / **將表轉成正常的範圍**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5586/14770657656_7b09ff14f6_z.jpg?resize=625%2C276" alt="Excel -> Design Ribbon -> Convert to Range" width="625" height="276" data-recalc-dims="1" /> 

按一下選擇把**表轉成正常的範圍**.. 會有一個彈出方塊叫大家**確定**  
<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2923/14813497073_041779842c_z.jpg?resize=369%2C138" alt="Do you want to convert the table to normal range?" width="369" height="138" data-recalc-dims="1" /> 

確定後這便移除在**Excel** 上的 **TFS Connection**

在**Team**的 **Ribbon**上..**Publish**的選項 **Grey out** 了

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3851/14607024148_a7b800355b_z.jpg?resize=625%2C290" alt="TFS Work Item on Excel Format disconnected with TFS Server" width="625" height="290" data-recalc-dims="1" /> 

Hope you find it useful