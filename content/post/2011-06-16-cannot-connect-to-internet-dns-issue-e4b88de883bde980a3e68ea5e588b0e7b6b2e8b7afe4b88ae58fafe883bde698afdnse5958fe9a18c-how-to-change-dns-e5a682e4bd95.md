---
id: 1800
title: 'Cannot Connect to Internet &#8211; DNS issue? &#8211; 不能連接到網路上可能是DNS問題? How to change DNS 如何更改電腦的DNS'
date: 2011-06-16T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1800
permalink: '/2011/06/cannot-connect-to-internet-dns-issue-%e4%b8%8d%e8%83%bd%e9%80%a3%e6%8e%a5%e5%88%b0%e7%b6%b2%e8%b7%af%e4%b8%8a%e5%8f%af%e8%83%bd%e6%98%afdns%e5%95%8f%e9%a1%8c-how-to-change-dns-%e5%a6%82%e4%bd%95/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
今天一早回到公司  
朋友便說公司的Internet Connection 出現了問題  
所有的Internet也不能連接到Internet上&#8230;  
我們公司有3個Broadband的&#8230;  
所以同一時間不能上網的機會很微..  
我們檢查了很久也找不到問題的出現..

每當我看網頁時便會出現以下畫面  
<img class="alignnone" title="Error 105 (net ERR_NAME_NOT_RESOLVED) Unable to Resolve the Server's DNS address" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f5beac998834401a9dc01ede16832f15/renditions/fullsize.jpg?resize=625%2C454" alt="" width="625" height="454" data-recalc-dims="1" />  
&#8220;<span style="color: #ff0000;">Error 105 (net ERR_NAME_NOT_RESOLVED) Unable to Resolve the Server&#8217;s DNS address</span>&#8221;  
最後有一個朋友提出..嘗試更改一下電腦的DNS 看看..  
我們便用了**Google 的DNS: 8.8.8.8**

**解決方法:**  
如何**更改電腦的DNS**

&#8220;**開始 / Start Menu**&#8220;->&#8221;**控制台 / Control Panel**&#8221; ->

[<img class="alignnone" title="Control Panel" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/09b3b2a53830415b956f46ac0fb68d48/renditions/fullsize.jpg?resize=625%2C469" alt="" width="625" height="469" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/09b3b2a53830415b956f46ac0fb68d48/renditions/fullsize.jpg)  
&#8220;**網路分享中心 / Network and Sharing Center**&#8221;  
[<img class="alignnone" title="Network and Sharing Center" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4b5948f5ff094a388afe84fe505642be/renditions/fullsize.jpg?resize=625%2C376" alt="" width="625" height="376" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4b5948f5ff094a388afe84fe505642be/renditions/fullsize.jpg)

按一下 “更改適配器設置 / Change Adapter Settings”  
[<img class="alignnone" title="Network Adapter Settings" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3846506d0b0f41349e24f4e801228877/renditions/fullsize.jpg?resize=625%2C373" alt="" width="625" height="373" data-recalc-dims="1" />](https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3846506d0b0f41349e24f4e801228877/renditions/fullsize.jpg)

-> 選擇你使用中的網路卡 ->按右制..選擇&#8221;內容&#8221;  
在&#8221;Networking&#8221; 分頁 選擇 &#8220;Internet Protocol Version 4 (TCP/IPv4)&#8221; 後按一下&#8221;內容 / Properties&#8221; 按鈕  
[<img class="alignnone" title="Local Area Connection Properties" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f3fa41a6a050481cbdb210ef1dc80302/renditions/fullsize.jpg?resize=380%2C469" alt="" width="380" height="469" data-recalc-dims="1" />](https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f3fa41a6a050481cbdb210ef1dc80302/renditions/fullsize.jpg)  
選擇 &#8220;Use the following DNS server addresses&#8221;  
[<img class="alignnone" title="DNS Settings" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e1fa0a52006142feac17b1c5783fab99/renditions/fullsize.jpg?resize=414%2C469" alt="" width="414" height="469" data-recalc-dims="1" />](https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e1fa0a52006142feac17b1c5783fab99/renditions/fullsize.jpg)  
之後在 &#8220;**Preferred DNS Server**&#8221; 上輸入 &#8220;**8.8.8.8**&#8221; <-Google 主要的DNS Server 地扯  
在&#8221;**Alternate DNS Server**&#8221; 上輸入 &#8220;**8.8.4.4**&#8221; <&#8211;Google 另一個DNS Server 地扯  
便可以了

這便解決了這個問題..  
最後發現..原來公司的Server 設定了我們使用其中一部Server 來做DNS 的  
因為這部Server的 Internet Connection 出現題..  
所以他不能找到外部的DNS 資料&#8230;  
每當看網頁時便會出現以下情況  
幸好..最後都能解決不能上網這個問題&#8230;

I cant live without internet&#8230;  
Hope you find it useful.