---
id: 3116
title: 'C# Get Hostname from string'
date: 2014-04-02T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3116
permalink: /2014/04/c-get-hostname-from-string/
categories:
  - .Net Tips And Tricks
---
今天公司的一個**Project**需要一個功能去取後網址上的**Hostname**

假設我們要取得**Hostname**的網址是這一個  
<a title="Azure Mobile Service Error" href="http://blog.sharechiwai.com/2014/03/azure-mobile-services-error-not-a-whitelisted-origin/" target="_blank">http://blog.sharechiwai.com/2014/03/azure-mobile-services-error-not-a-whitelisted-origin/</a>

**解決方法**十分簡單..  
我們可以使用建立一個**Uri Object**

之後使用他的**Host**屬性來取得 這個網址的**Hostname**  
如果這個字串不是網址的話..  
在建立**Uri Object**時  
便會出現&#8221;<span style="color: #ff0000;"><strong>UriFormatException</strong></span>&#8220;的錯誤  
<img class="alignnone" alt="UriFormatException" src="https://i0.wp.com/farm8.staticflickr.com/7197/13597919953_3b64c6a337_d.jpg?resize=458%2C403" width="458" height="403" data-recalc-dims="1" /> 

**E.G.**

[csharp]  
string url = "http://blog.sharechiwai.com/2014/03/azure-mobile-services-error-not-a-whitelisted-origin/";  
Uri myUri = new Uri(url);  
string host = myUri.Host;  
// Show result  
MessageBox.Show(host);

[/csharp]

他便會彈出 &#8220;<a title="ShareChiWai Tech Blog" href="http://blog.sharechiwai.com" target="_blank"><strong>blog.sharechiwai.com</strong></a>&#8220;了  
<img class="alignnone" alt="blog.sharechiwai.com Url Pop-up" src="https://i1.wp.com/farm4.staticflickr.com/3826/13598259714_14cddf2105_d.jpg?resize=219%2C186" width="219" height="186" data-recalc-dims="1" /> 

Hope you find it useful