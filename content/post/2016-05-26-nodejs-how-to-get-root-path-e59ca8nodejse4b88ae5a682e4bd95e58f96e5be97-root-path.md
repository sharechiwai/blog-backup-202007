---
id: 3685
title: 'NodeJs how to get root path &#8211; 在NodeJs上如何取得 Root Path'
date: 2016-05-26T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3685
permalink: '/2016/05/nodejs-how-to-get-root-path-%e5%9c%a8nodejs%e4%b8%8a%e5%a6%82%e4%bd%95%e5%8f%96%e5%be%97-root-path/'
categories:
  - NodeJs
tags:
  - NodeJs
---
今日嘗試在**Route** 檔案上**load**我的config file  
E.G.

<pre>var config = require('./config/config');
</pre>

誰不知..  
當我執行我的**NodeJs Application** 時出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Error: Cannot find module &#8216;./config/config&#8217;</strong></span>&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7264/27213994405_74173f8652_z.jpg?resize=625%2C231" alt="Error: Cannot find module './config/config'" width="625" height="231" data-recalc-dims="1" /> 

**解決方法**是只要我們可以Reference **Full Path** E.G. 包含 **Root Directory** 應該便可以解決這個問題  
我們可以使用 &#8220;**path**&#8220;這一個module  
之後使用他的**path.dirname**功能去取得  
**require.main.filename** &#8211; <span style="color: #3366ff;"><strong>執行的js path location</strong></span>

**解決方法**

<pre>var path = require('path');
var appDir = path.dirname(require.main.filename);

console.log(appDir);
var config = require(appDir + '/config/config');
</pre>

結果:  
<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7365/27145009991_cc4a535732_z.jpg?resize=437%2C94" alt="Print root directory" width="437" height="94" data-recalc-dims="1" /> 

Hope you find it useful