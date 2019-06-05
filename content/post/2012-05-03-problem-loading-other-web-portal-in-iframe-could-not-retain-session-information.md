---
id: 2429
title: 'Problem loading other web portal in iframe &#8211; could not retain session information'
date: 2012-05-03T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2429
permalink: /2012/05/problem-loading-other-web-portal-in-iframe-could-not-retain-session-information/
categories:
  - Experience Share / 經驗分享
tags:
  - viewing cross-domain web content in IE
---
今天有客人打電話來說他們的用戶不能登入我們的Web Portal..  
看了一看&#8230; 用**Google Chrome** 和**FireFox**都沒有問題..  
在IE 上便可以Replicate問題了

到最後終於找到了解決方法了&#8230;  
就是要更改以下的 **IE Settings**.

**解決方法:**  
在IE 的**Tool bar** 選擇 &#8220;**Internet Options**&#8221;  
[<img class="alignnone" title="Internet Options" src="https://i1.wp.com/farm6.static.flickr.com/5167/5366613897_209d4f92f0.jpg?resize=500%2C318" alt="" width="500" height="318" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5167/5366613897_209d4f92f0.jpg)  
之後按一下&#8221;**Security**&#8221; Tab, 之後選擇 &#8220;**Trusted Site**&#8221; -> 再按一下&#8221;**Site**&#8221; 按鈕  
E.G. 選擇 **&#8220;Tools&#8221; -> &#8220;Internet Options&#8221; ->&#8221;Security&#8221; Tab ->&#8221;Trusted Site&#8221; ->&#8221;Site&#8221;** 按鈕  
[<img class="alignnone" title="Trusted Site" src="https://i2.wp.com/farm6.static.flickr.com/5203/5367226306_8865cc7514.jpg?resize=391%2C500" alt="" width="391" height="500" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5203/5367226306_8865cc7514.jpg)

之後輸入你使用的網址..之後按&#8221;**Add**&#8221; 把網址加入到&#8221;**Trusted Site**&#8220;-> 之後&#8221;**Close**&#8220;關閉這個Page  
[<img class="alignnone" title="Add CRM to trusted Site" src="https://i0.wp.com/farm6.static.flickr.com/5247/5366613923_6b74a918c7.jpg?resize=394%2C348" alt="" width="394" height="348" data-recalc-dims="1" />](http://www.flickr.com/photos/sharechiwai/5366613923/)  
按一下&#8221;**Custom Level**&#8221; 去更變一些設定  
在&#8221;**Security Settings &#8211; Trusted Sites Zone**&#8221; 中找出  
在&#8221;**Security Settings &#8211; Trusted Sites Zone**&#8221; 中找出  
&#8220;**Miscellaneous**&#8220;->&#8221;**Access data sources across domains**&#8221; section  
之後選擇 &#8220;Enable&#8221;  
按 &#8220;**OK**&#8221; 便可&#8230;  
<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3910/14518644026_bb338a6e2c_z.jpg?resize=432%2C495" alt="IE -> Security Settings -> Access data sources across domains" width="432" height="495" data-recalc-dims="1" /> 

Hope you find it useful