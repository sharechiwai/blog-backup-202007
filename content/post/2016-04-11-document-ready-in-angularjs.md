---
id: 3609
title: Document.Ready in AngularJs
date: 2016-04-11T16:33:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3609
permalink: /2016/04/document-ready-in-angularjs/
categories:
  - AngularJs
tags:
  - AngularJs
  - Jquery
---
相信很多朋友都有使用**JQuery**來 寫網頁&#8230;  
大家對**document.ready**都不會陌生&#8230;

當大家轉了使用AngularJs的時候都可能會有一個 疑問&#8230;  
如何在 **AngularJS** 上使用 **document.ready**?

**解決方法**十分簡單

我們可以使用<span style="color: #339966;"><strong>angular.element(document).ready()</strong> </span>來實現 <span style="color: #339966;"><strong>document.ready</strong> </span>待 html成功load完之後執行 **document.ready**入的程式碼

<pre>angular.element(document).ready(function () {
        console.log('Hello World');
    });
</pre>

E.G.

<pre>angular.module("shareChiWaiApp", [])
    .controller("shareChiWaiCtrl", ["$scope", function ($scope) {

        function shareChiWaiViewModel() {
            var self = this;
            self.firstName = "ChiWai";
            self.surname = "Share";
        }

        
        
        angular.element(document).ready(function () {
        $scope.sharechiwai = new shareChiWaiViewModel();
          $scope.sharechiwai.firstName="before";
        console.log($scope.sharechiwai.firstName);
        });
    }]);
</pre>

Hope you find it useful