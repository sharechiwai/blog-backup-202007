---
id: 1776
title: 'Web Service Testing tools &#8211; WCF Test Client'
date: 2011-06-01T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1776
permalink: /2011/06/web-service-testing-tools-wcf-test-client/
categories:
  - WCF
---
最近因為公司更換了Server ..但是又沒有好好設計到和舊的Server 一樣的關係, 令到公司其中一個**WCF Web Services** 出現了 **Localisation** 的問題&#8230;  
這個**Web Service** 和 在**CodePlex** 上的 **Crystal Report WCF Services** <a title="Crystal Report WCF Services" href="http://crystalrptwcfservice.codeplex.com/" target="_blank">http://crystalrptwcfservice.codeplex.com/</a> 的差不多.. 只是加了更多和公司相關的功能入去..方便公司生產在Web Site 上 便用這個 **Web Services** 來生產 **PDF**..  
由於這個Web Services 把公司用開的英鎊符號..變成了美金&#8230;  
所以常常都使用**WCFTestClient**來測試這個Web Services..  
最初我懂得在**Visual Studio 上在WCF Debug** 時便用這個**WCFTestClient**..  
之後在上面加入要測試的**Web Services Address**..

今天我終於找到了這個**WCFTestClient.exe** 存在那裡..  
現在建立了一個Desktop Short-cut 方便自己將來調試更多的Web Services  
大家可以在這個路徑上找到..十分好用的&#8230;  
當我在測試其他WCF或Web Service時我也使用他的  
**C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\WCFTestClient.exe**

[<img class="alignnone" title="WCF Test Client" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8fe5cc84c1454eb5abae8337ebcc6725/renditions/fullsize.jpg?resize=625%2C392" alt="" width="625" height="392" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8fe5cc84c1454eb5abae8337ebcc6725/renditions/fullsize.jpg)  
Hope you find it useful

*最後解決這個**Localisation** 問題的方法是在這個**WCF Services**上的**IIS** 更變一些有關**Localisation** 的設定..從啟主機後便解決了這個問題