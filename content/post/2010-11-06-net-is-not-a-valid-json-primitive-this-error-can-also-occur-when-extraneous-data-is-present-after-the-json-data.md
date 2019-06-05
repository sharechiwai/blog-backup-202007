---
id: 887
title: '.Net &#8221; is not a valid JSON primitive. This error can also occur when extraneous data is present after the JSON data.'
date: 2010-11-06T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=887
permalink: /2010/11/net-is-not-a-valid-json-primitive-this-error-can-also-occur-when-extraneous-data-is-present-after-the-json-data/
categories:
  - .Net Tips And Tricks
  - Javascript
  - PHP 新手筆記
  - Silverlight Tips and Tricks
---
今日又再開始接觸 **Silverlight Application** 了  
最近學會了用**PHP** 的 **Codeigniter RESTFul Framework**  
可以很簡單地建立一個**RESTFul Services**

但當我嘗試到**deserialize** json 的時候..  
我出現了以下的問題  
**<span style="color: #ff0000;">&#8221; is not a valid JSON primitive. This error can also occur when extraneous data is present after the JSON data.</span>**

最後發現原來自己的**RESTFul Output** 是一個 **XML 的Output&#8230;**  
所以便出現了這個問題了

如果大家有相同的問題時  
可以查看**JSON** 的 結果是不是 正確的..  
可能JSON 你想接收到的不是一個正確的JSON =P

Hope you find it useful