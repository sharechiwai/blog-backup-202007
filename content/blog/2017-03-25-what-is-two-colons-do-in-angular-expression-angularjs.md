---
id: 3958
title: 'What is two colons do in angular expression {{::}}? 在AngularJs上雙 :: 是什麼意思?'
date: 2017-03-25T00:00:54+08:00
author: ShareChiWai
layout: post
categories:
  - AngularJs
tags:
  - AngularJs
  - Code Review
---

今日**Code Review** 時見到同事在 **AngularJs**的 project 上 使用了

<pre>{::ctrl.title}
</pre>

起初還以為是把打錯字
做了一會 research 之後發現
原來 **{{::}}** 是 **One-time Binding** 的意思
就是說**即使 在 controller 的 variable 的內容有改變**
**這個 one-time binding 的 value** 也不會改變
詳情可以參考以下網頁
<https://docs.angularjs.org/guide/expression#one-time-binding>

Hope you find it useful
