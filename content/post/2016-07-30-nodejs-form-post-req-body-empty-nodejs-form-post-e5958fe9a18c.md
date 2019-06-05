---
id: 3708
title: 'NodeJs Form Post req.body empty &#8211; NodeJs Form Post 問題'
date: 2016-07-30T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3708
permalink: '/2016/07/nodejs-form-post-req-body-empty-nodejs-form-post-%e5%95%8f%e9%a1%8c/'
categories:
  - NodeJs
tags:
  - NodeJs
---
在學習**NodeJs**時嘗試建立一個簡單的 **Contact Form**  
**Post Data** 到**Backend** 之後便用 **Email API 去Email Contact Form** 的內容給自己  
做了很多Research 都是取不到 **Contact form** 的 **parameters**

好多教學都是這樣 define &#8220;<span style="color: #008080;"><strong>body-parser&#8221;</strong></span> 便可以  
我的**NodeJs BackEnd** 程式碼  
希望收到資料之後 用**nodeJs** 的**Console**把 收到的email 輸出來  
用來**debug**. 去確保我程式碼真的做到想做的功能  
可惜都是不成功

以下昰小弟最後的製成品..  
希望有用吧

**解決方法**

E.g.

<pre>var express = require('express');

// Body Parser need to declare on app.js,
// tried to declare on the route and it does not work
var bodyParser = require('body-parser');
var app = express();
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({extended : true}));
// my route for the contact form
    homeRouter.route('/contact')
        .get(function(req, res) {
            res.render('home/index', {
                title: 'ShareChiWai',
                nav: nav,
                content: 'contact'
            });
        })
// route for the function to sent email
  homeRouter.route('/emailSent')
    .post(function(req, res) {
      console.log("Begin");
      console.log(req.body.email);
      console.log("end");
    
      res.send(req.body.email);
    });
</pre>

**Full source code** 可以參考我在GitHub上的程式碼  
<https://github.com/sharechiwai/NodeExpress>  
有時間希望可以一個full demo 只是for contact form.

**Main Application**  
<https://github.com/sharechiwai/NodeExpress/blob/master/app.js>

**Home Route**  
<https://github.com/sharechiwai/NodeExpress/blob/master/src/routes/homeRoutes.js>

Hope you find it useful