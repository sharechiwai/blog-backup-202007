---
id: 3700
title: 'Solve nodejs Access-Control-Allow-Origin header Issue 如果在NodeJS上解決&#8221;Access-Control-Allow-Origin header&#8221; 問題'
date: 2016-07-25T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3700
permalink: '/2016/07/solve-nodejs-access-control-allow-origin-header-issue-%e5%a6%82%e6%9e%9c%e5%9c%a8nodejs%e4%b8%8a%e8%a7%a3%e6%b1%baaccess-control-allow-origin-header-%e5%95%8f%e9%a1%8c/'
categories:
  - NodeJs
tags:
  - Access-Control-Allow-Origin header
  - API
  - NodeJs
---
之前在**NodeJs**寫了一個**API** 來方便自己去取資料..  
誰不知當我在其他網頁用這個**API** 時出現了&#8221;<span style="color: #ff0000;"><strong>Access-Control-Allow-Origin header</strong></span>&#8221; 的問題..

<img class="alignnone" src="http://i1.wp.com/farm9.static.flickr.com/8628/27965914454_056f4b8f14_z.jpg?resize=625%2C128" alt="Origin file: not found in Access-control-Allow-Origin header." width="625" height="128" />  
“<span style="color: #ff0000;"><strong>Origin file: not found in Access-Control-Allow-Origin header</strong></span>”

做了一會Research後 找到了解決方法了  
我們只需要加入以下的&#8221;**allowCrossDomain**&#8221; 功能 便可以了  
**解決方法**

<pre>var express = require('express');

var app = express();

// Code to solve the Access-Control-Allow-Origin header Issue
var allowCrossDomain = function(req, res, next) {
    res.header('Access-Control-Allow-Origin', '*');
    res.header('Access-Control-Allow-Methods', 'GET,PUT,POST,DELETE,OPTIONS');
    res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization, Content-Length, X-Requested-With');

   // intercept OPTIONS method
    if ('OPTIONS' == req.method) {
      res.send(200);
    }
    else {
      next();
    }
};


app.use(allowCrossDomain);
</pre>

Hope you find it useful