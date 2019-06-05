---
id: 2084
title: 'How to create a link for dial Telephone Number for mobile web page- 手機版網頁- 如何製作打電話的連結'
date: 2011-09-06T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2084
permalink: '/2011/09/how-to-create-a-link-for-dial-telephone-number-for-mobile-web-page-%e6%89%8b%e6%a9%9f%e7%89%88%e7%b6%b2%e9%a0%81-%e5%a6%82%e4%bd%95%e8%a3%bd%e4%bd%9c%e6%89%93%e9%9b%bb%e8%a9%b1%e7%9a%84%e9%80%a3/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - HTML
---
今天有朋友問..  
為什麼有一些網頁在手機上看..  
之後按一下和電話號碼相關的地方/連結便會問你是不是想撥號..  
想知道怎樣實行的

**解決方法** 十分簡單  
在HTML 上的 **Anchor Tag** 中的 Href 的屬性 可以加入不同的**Prefix**來實現不同的動作的  
tel:  
E.G  
**撥號**  
**tel:** 在手機上會問你是否要撥號/電腦上可能會有一個和打電話相關的程式出現問你是否要撥號  
<span style="color: #3366ff;"><strong> <a href=&#8221;tel:01235678&#8243; >致電給我</a></strong></span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b1c4d0190bc74189988d40d435ab7846" alt="href=tel: option use communicator to dial number" width="459" height="318" />  
**mailto:** 電子郵箱的連結..會用你的Email Client開啟的  
<span style="color: #3366ff;"><strong> <a href=&#8221;mailto:email@domain.com&#8221; >Email me</a></strong></span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d3e0a30b1a57458ab65b45bc5ea9ab7a" alt="href=mailto: option Email Client Outlook" width="542" height="430" />  
**file:** 這一個和㠪常的超連結分別不大  
<span style="color: #3366ff;"><strong> <a href=&#8221;file:d:\OpenXMLSDKv2.msi&#8221; >Download</a></strong></span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1125322769b944e9aac01fc154b6fa3a" alt="HREF file: option to download file" width="678" height="456" />  
**javascript:** 執行Javascript  
<span style="color: #3366ff;"><strong><a href=&#8221;javascript:alert(&#8216;Welcome to Share ChiWai&#8217;)&#8221; > Welcome to ShareChiWai</a></strong></span>

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8cb803d386904741a92bd2c13549ce3c" alt="HREF javascript: option to trigger javascript action" width="426" height="161" /> 

Hope you find it useful