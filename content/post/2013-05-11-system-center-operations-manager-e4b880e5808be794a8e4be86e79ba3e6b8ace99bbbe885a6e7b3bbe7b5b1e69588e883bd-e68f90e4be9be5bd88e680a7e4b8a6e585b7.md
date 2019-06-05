---
id: 2862
title: 'System Center Operations Manager &#8211;  一個用來監測電腦系統效能, 提供彈性並具成本效益的基礎結構監視的功具'
date: 2013-05-11T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2862
permalink: '/2013/05/system-center-operations-manager-%e4%b8%80%e5%80%8b%e7%94%a8%e4%be%86%e7%9b%a3%e6%b8%ac%e9%9b%bb%e8%85%a6%e7%b3%bb%e7%b5%b1%e6%95%88%e8%83%bd-%e6%8f%90%e4%be%9b%e5%bd%88%e6%80%a7%e4%b8%a6%e5%85%b7/'
categories:
  - System Center Operations Manager
tags:
  - SCOM
---
最近老闆感到公司的電腦系統/伺服器 等都像有點效能問題..  
和感覺上公司的系統和網絡都有些不穩定..  
有些**Server Visualise** 了 但是在資源連用上好像不太完善  
有些**Server**把所多會用很多資源的 **Virtual Machine**放在一起..  
令到效能不好[**server** 運作很慢]  
有些卻把一些不需要太多的資源的 **Server** 放在同一個 Host上.  
令到資源浪費&#8230;

另一個很嚴重的問題是&#8230;  
公司的**Exchange Server**有一天居然沒有**Free Space**  
令到**Exchange Server** 不能運作..  
這是一個做**System Admin** 或 管理公司的系統的人不能犯錯的 事情  
避免公司再有這些問題出現..

老闆希望可以使用一些軟體**去監測/檢查**一下  
公司的**電腦系統/伺服器/ 網絡的健康狀況**..

可以未雨綢繆..在出現狀況之前/或出現情況時會發電郵/短信給我們&#8230;  
以減少公司系統的 **Down time**.

做了一會兒Research &#8211; 和問了朋友意見之後..  
朋友建議我可以使用 **System Center Operations Manager** (**SCOM**)  
他可以做以下的東西:

**System Center 2012 – Operations Manager** 提供彈性並具成本效益的基礎結構監視、協助確保重要應用程式的可預測效能和可用性，並為私人和公用資料中心和雲端提供全方位的監視。

<a title="System Center 2012 Operations Manager" href="http://technet.microsoft.com/zh-tw/library/hh205987.aspx" target="_blank">http://technet.microsoft.com/zh-tw/library/hh205987.aspx<br /> <a href="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SCOMFirstStart.jpg"><img class="alignnone size-full wp-image-2863" alt="System Center 2012 Operations Manager" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SCOMFirstStart.jpg?resize=625%2C443" width="625" height="443" data-recalc-dims="1" /></a><br /> </a>

在將來的日子希望可以和大家分享我在設定和使用 System Center Operations Manager SCOM 的經驗

Hope you find it useful