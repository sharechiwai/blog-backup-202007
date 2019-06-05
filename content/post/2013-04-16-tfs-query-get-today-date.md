---
id: 2756
title: TFS query get Today Date
date: 2013-04-16T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2756
permalink: /2013/04/tfs-query-get-today-date/
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - TFS
---
最近開始好好運用**TFS** 來管理自己的工作.. [和開發有關的**Task**我也放進了**TFS** 裡&#8230;]  
雖然還沒有時間解決**Reporting Service**的問題..  
但是都要以**最佳實踐** **Best Practices** 做好練習..  
E.G. 如果還要等所有東西設定好時才開始好好使用的話..  
將會失去現在的記錄&#8230;

由於每星期都要向上司提交一個工作報告..  
[原本想在**reporting service**設定好時便可以好好的建立一個報表給他自己看..]  
所以現在想在**TFS** 上寫一個簡單的**Query** 方便自己顯示過去7天工作做了什麼..

當我嘗試寫的時候發現..  
其實我之前沒有寫過的..心想..他的**Query** 應該都是和**TSQL** 差不多的..  
所以我便嘗試用<span style="color: #3366ff;"><strong> GETDATE()</strong></span>試試看..  
可惜&#8230;<span style="color: #3366ff;"><strong>GETDATE</strong></span>不能用..

那麼怎樣才可以在**TFS Query** 的今日日期的變數是怎樣呢?

原來解決方法十分簡單  
**解決方法**:  
我們可以使用 <span style="color: #3366ff;"><strong>@Today</strong></span>  
來找到今天的日子..之後用 [<span style="color: #3366ff;"><strong>Changed Date > @Today &#8211; 7</strong></span> ] 便可以找到過去7 天做了什麼了  
[<img class="alignnone size-full wp-image-2757" alt="TFS Query Get Today Date" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TFS-Query-Get-Today-Date.jpg?resize=625%2C205" width="625" height="205" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TFS-Query-Get-Today-Date.jpg)

Hope you find it useful