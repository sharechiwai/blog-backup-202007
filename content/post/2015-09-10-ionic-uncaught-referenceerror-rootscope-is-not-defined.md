---
id: 3500
title: 'Ionic Uncaught ReferenceError: $rootScope is not defined'
date: 2015-09-10T20:13:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3500
permalink: /2015/09/ionic-uncaught-referenceerror-rootscope-is-not-defined/
categories:
  - Ionic Framework
tags:
  - ionic troubleshooting
  - Mobile Development
---
今天在**ionic** application 上需要使用到 <span style="color: #008000;"><strong>$rootScope</strong></span>  
當我執行這個**app**時出現了以下的錯誤信息

<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/737/20492171699_170a7201d1_z.jpg?resize=625%2C132" alt="Uncaught ReferenceError: $rootScope is not defined" width="625" height="132" data-recalc-dims="1" />  
**解決方法**十分簡單  
我們只需要在 **function**上加上 <span style="color: #008000;"><strong>$rootScope</strong></span> 這個**dependency** 便可以了

**E.G.**

<pre>.run(function ($ionicPlatform, <strong> $rootScope</strong>) {
    $rootScope.$on("", function(){});
  
  }

</pre>

Hope you find it useful