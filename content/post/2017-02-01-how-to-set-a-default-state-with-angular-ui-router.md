---
id: 3828
title: How to set a default state with Angular ui-router
date: 2017-02-01T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3828
permalink: /2017/02/how-to-set-a-default-state-with-angular-ui-router/
categories:
  - AngularJs
tags:
  - AngularJs
  - routing
  - ui-route
---
最近使用了 **Angular Js** 的 **ui-route** 來作我的js demo 的 **navigation**

之後發現一個問題  
就是**當URL 輸入錯的時間便會出現問題**  
那麼怎樣可以把設定一個把這些Request 直接連到一個page not found

**解決方法**十分簡單

我們可以在定義這個Module 設計route的時候設定 &#8220;<span style="color: #3366ff;"><strong>$urlRouterProvider</strong></span>&#8221;  
之後在module內定義一個**Default route** 將去到的路徑 **<span style="color: #3366ff;">$urlRouterProvider.otherwise</span>**  
e.g.

<pre>$urlRouterProvider.otherwise('/home');
//或
  $urlRouterProvider.otherwise('/page-not-found');
</pre>

便可以了  
e.g.

<pre>var jsDemoApp = angular.module('jsDemoApp', ['ui.router']);

// configure our routes
jsDemoApp.config(['$locationProvider', '$stateProvider', '$urlRouterProvider', function ($locationProvider, $stateProvider, $urlRouterProvider) {
    $urlRouterProvider.otherwise('/home');
    $stateProvider
        // HOME PAGE ========================================
        .state('home', {
            url: '/home',
            templateUrl: '/modules/js-demo/views/index.html',
            abtract: true
        })
        // ABOUT PAGE
        .state('about', {
            url: '/about',
            templateUrl: '/modules/js-demo/views/about.html',
            abtract: true
        });
  }]);

</pre>

Hope you find it useful