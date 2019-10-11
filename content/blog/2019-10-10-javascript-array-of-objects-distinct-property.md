---
title: 'How to get distinct values from an array of objects in JavaScript '
date: 2019-06-25T00:00:00+08:00
author: ShareChiWai
layout: post
categories:
  - Javascript
tags:
  - NodeJs, Javascript, ES5
---

使用 firebase hosting 來 host reactjs 既時候 出現了以下問題
當我直接在 browser 輸入 ReactJs 的 route 既時候 出現了

```
Page Not Found
This file does not exist and there was no index.html found in the current directory or 404.html in the root directory

```


_解決方法:_
我們只需要在 `firebase.json` 的 `hosting` section
加上 `rewrites` 到 index.html 便可以了

```
 var ports = arr.map( // try to retrieve specific property
        function(item) {
          return item.interestedProperty;
        }) // Distinct
        .filter(function(item, index, arr){
          return arr.indexOf(item) === index;
        }) // sort
        .sort();

```

Hope you find it useful
