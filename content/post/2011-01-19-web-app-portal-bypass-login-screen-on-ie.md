---
id: 1156
title: Web App Portal Bypass Login screen on IE
date: 2011-01-19T00:00:34+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1156
permalink: /2011/01/web-app-portal-bypass-login-screen-on-ie/
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
今日公司開始使用**Microsoft Dynamics CRM 4.0**, 主要是用來做**Project Management**, **Task Lists**, **Feature Request**, **Bug Tracking** 等等  
安裝方法很簡單&#8230;  
又可以用**Windows Authentication**來登錄這個**Web Portal.**..

但不知道為什麼&#8230;每次Load up這個**Web Portal**時..  
都會需要輸入**Username/Password**的..  
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
&#8220;**User Authentication**&#8221; ->&#8221;**Logon**&#8221; section  
之後選擇 &#8220;**Automatic logon with current user name and password**&#8221;  
按 &#8220;**OK**&#8221; 便可&#8230;  
[<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5287/5366614023_d3f936b9c6.jpg?resize=427%2C485" alt="https://i0.wp.com/farm6.static.flickr.com/5287/5366614023_d3f936b9c6.jpg?resize=427%2C485" width="427" height="485" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5287/5366614023_d3f936b9c6.jpg)

Hope you find it useful