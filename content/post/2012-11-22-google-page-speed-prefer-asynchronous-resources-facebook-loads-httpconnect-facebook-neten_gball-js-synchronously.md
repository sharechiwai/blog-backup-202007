---
id: 2595
title: 'Google Page Speed Prefer asynchronous resources (Facebook)- loads http://connect.facebook.net/en_GB/all.js synchronously.'
date: 2012-11-22T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2595
permalink: /2012/11/google-page-speed-prefer-asynchronous-resources-facebook-loads-httpconnect-facebook-neten_gball-js-synchronously/
categories:
  - Web Optimisation
tags:
  - facebook
---
最近為自己的網頁<a title="智慧分享" href="http://sharechiwai.com" target="_blank">http://sharechiwai.com</a> 加上了 Facebook social plugin  
希望大家給我多一些 **Like** **讚**多一些我  
誰不知 當我使用**Google Page Speed**我測試 sharechiwai.com的性能時  
卻出現了以下的建議

&#8220;<span style="color: #ff6600;"><em>Prefer asynchronous resources &#8211; Fetching resources asynchronously prevents those resources from blocking the page load.</em></span>  
<span style="color: #ff6600;"><em> Suggestions for this page</em></span>

**<span style="color: #ff6600;"><em>The following resources are loaded synchronously. Load them asynchronously to reduce blocking of page rendering.</em></span>**  
**<span style="color: #ff6600;"><em> http://localhost:8080/sharechiwai/lookforhk loads http://connect.facebook.net/en_GB/all.js synchronously.</em></span>**&#8221;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d965ad7175a84069ac5f5e6dddd82d64" alt="load http://localhost:8080/sharechiwai/lookforhk loads http://connect.facebook.net/en_GB/all.js synchronously." width="767" height="315" />  
是存取**facebook**的**Javascript Plugin** 的方法所導致的

[javascript]

<script>(function(d, s, id) {  
var js, fjs = d.getElementsByTagName(s)[0];  
if (d.getElementById(id)) return;  
js = d.createElement(s); js.id = id;  
js.src = "//connect.facebook.net/en_GB/all.js#xfbml=1&appId=277649966574";  
fjs.parentNode.insertBefore(js, fjs);  
}(document, &#8216;script&#8217;, &#8216;facebook-jssdk&#8217;));</script>  
[/javascript]

做了一會兒research 之後找到了解決方法了

**解決方法**:  
原來這個**facebook Javascript Object** 上有一個**async**的屬性 property  
我們只要把他設定為 **true**便可以解決  
e.g.

[javascript]  
js.async=true;  
[/javascript]

&#8220;<span style="color: #ff6600;"><strong>loads http://connect.facebook.net/en_GB/all.js synchronously.</strong></span>&#8220;的問題了

[javascript]

<script>(function(d, s, id) {  
var js, fjs = d.getElementsByTagName(s)[0];  
if (d.getElementById(id)) return;  
js = d.createElement(s); js.id = id;  
js.async=true; //<&#8211;ASYNC = TRUE  
js.src = "//connect.facebook.net/en_GB/all.js#xfbml=1&appId=277649966574";  
fjs.parentNode.insertBefore(js, fjs);  
}(document, &#8216;script&#8217;, &#8216;facebook-jssdk&#8217;));</script>  
[/javascript]

Hope you find it useful