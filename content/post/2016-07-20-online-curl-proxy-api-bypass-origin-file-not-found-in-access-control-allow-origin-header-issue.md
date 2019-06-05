---
id: 3695
title: 'Online cURL Proxy / API &#8211; bypass Origin file: not found in Access-Control-Allow-Origin header issue'
date: 2016-07-20T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3695
permalink: /2016/07/online-curl-proxy-api-bypass-origin-file-not-found-in-access-control-allow-origin-header-issue/
categories:
  - Experience Share / 經驗分享
tags:
  - API
  - cURL
  - NodeJs
---
很多時候找到一些有趣的**API** 時  
我們可以直接把這個**API** 的**URL** 和**Query String**放在browser上而取得Data  
但當我們使用**Javascript** E.G. **JQuery** **$.get** 時便會出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Origin file: not found in Access-Control-Allow-Origin header</strong></span>&#8221;  
和  
&#8220;<span style="color: #ff0000;"><strong>XMLHttpRequest: Network Error 0x80700013, Could not complete the operation due to error 80700013</strong></span>.&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm9.static.flickr.com/8628/27965914454_056f4b8f14_z.jpg?resize=625%2C128" alt="Origin file: not found in Access-control-Allow-Origin header." width="625" height="128" data-recalc-dims="1" /> 

**解決方法**  
我們可以用**cURL** 來解決這個問題..  
由於我久不久便有這個問題出現..  
所以便用**nodeJS** 來起了一個功能和大家分享.  
&#8216;**http://sharechiwainodeexpress.herokuapp.com/curl?url={URL-to-CURL}**&#8216;

E.g.  
&#8216;[**http://sharechiwainodeexpress.herokuapp.com/curl?url=http://blog.sharechiwai.com**](http://sharechiwainodeexpress.herokuapp.com/curl?url=http://blog.sharechiwai.com)&#8216;

可以用他當作proxy 吧

Hope you find it useful