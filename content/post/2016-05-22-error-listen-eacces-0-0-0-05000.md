---
id: 3672
title: 'Error: Listen EACCES 0.0.0.0:5000'
date: 2016-05-22T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3672
permalink: /2016/05/error-listen-eacces-0-0-0-05000/
categories:
  - NodeJs
tags:
  - Express
  - NodeJs
  - NodeJs Troubleshooting
---
今日嘗試好好地寫一個**Node JS** With **Express** 的**Web Application**  
來練習一下自己的**NodeJS** Skill  
誰不知當我 執行 **node app.js** 時  
出現了以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Error: Listen EACCES 0.0.0.0:5000</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7249/27119336511_349ffc5322_z.jpg?resize=625%2C217" alt="Error: Listen EACCES 0.0.0.0:5000" width="625" height="217" data-recalc-dims="1" />  
做了一會research之後發現這是因為電腦上同一個Port e.g. **port :5000**  
正在被使用中..  
所以便有這個error.  
之後發現原來電腦上的**IIS** 其中一個**virtual directory**正在使用 **port 5000**

**解決方法**十分簡單  
只需要更改了 **NodeJs** 執行的Port便可以了  
E.G.

<pre>var express = require('express');

var app = express();

var port = process.env.PORT || 3000;

app.listen(port, function(err) {
    console.log('running server on port ' + port);
});

</pre>

Hope you find it useful