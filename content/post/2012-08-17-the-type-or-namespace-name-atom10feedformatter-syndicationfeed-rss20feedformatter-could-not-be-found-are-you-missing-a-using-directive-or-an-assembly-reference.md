---
id: 2553
title: 'The type or namespace name &#8216;Atom10FeedFormatter&#8217;, &#8216;SyndicationFeed&#8217;, &#8216;Rss20FeedFormatter&#8217; could not be found (are you missing a using directive or an assembly reference?)'
date: 2012-08-17T00:00:33+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2553
permalink: /2012/08/the-type-or-namespace-name-atom10feedformatter-syndicationfeed-rss20feedformatter-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference/
categories:
  - .Net Tips And Tricks
tags:
  - SyndicationFeed
---
今天嘗試把之前寫的 **.Net 4 Library**升級到 **.Net 4.5**  
我用了一個很原始的放法..  
就是Copy and Paste了..  
因為想和自己做一次**Code-Review**..  
每當回顧自己之前寫的程式碼時..  
都會感到很有趣..  
原來自己之前寫的程式碼是那麼的不成熟的..  
當時還以為自己的程度不太差.  
誰不知&#8230;原來自己還有很大的進步空間

今天升級時遇到的問題有..  
當我Copy and Paste我的**Class Library** 時出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>The type or namespace name &#8216;Atom10FeedFormatter&#8217;could not be found (are you missing a using directive or an assembly reference?)</strong></span>&#8221;  
&#8220;<span style="color: #ff0000;"><strong>The type or namespace name &#8216;SyndicationFeed&#8217;could not be found (are you missing a using directive or an assembly reference?)</strong></span>&#8221;  
&#8220;<span style="color: #ff0000;"><strong>The type or namespace name &#8216;Rss20FeedFormatter&#8217;could not be found (are you missing a using directive or an assembly reference?)</strong></span>&#8221;  
原因是因為忘記了..他們需要引用那些的DLL 和Namespace.

做了一會research後 問題終止解決了  
要使用&#8217;**Atom10FeedFormatter**&#8216;, &#8216;**SyndicationFeed**&#8216;, &#8216;**Rss20FeedFormatter**&#8216;的話  
我們是需要用到 &#8220;**System.ServiceModel.Syndication**&#8221; 這個Namespace的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/82be7f4359d74fa48a3e3b5fcf9e488f" alt="System.ServiceModel.Syndication" width="856" height="118" />  
如果要使用到 **System.ServiceModel.Syndication namespace** 的話  
我們便需要在Project 上加入以下的參考&#8221;**DLL**&#8220;了  
&#8220;**System.ServiceModel**&#8221;  
**解決方法**:  
在**Project**上的**Reference** 資料夾上按右鍵  
選擇&#8221;**Add Reference&#8230;**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/771d3df22c08410499a9091446d82886" alt="add reference" width="424" height="375" />  
之後在&#8221;**Reference Manager**&#8221; 上選擇 &#8220;**System.ServiceModel**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/30cf1dbd21484417842cb9f980222343" alt="Reference Manager" width="814" height="575" />  
按下&#8221;**OK**&#8221; 便可

Hope you find it useful