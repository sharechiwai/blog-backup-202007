---
id: 3830
title: Disable HTML A HREF tag action
date: 2017-01-31T22:42:32+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3830
permalink: /2017/01/disable-html-a-href-tag-action/
categories:
  - HTML/CSS
tags:
  - Javascript
  - Javascript Tips and tricks
---
今日要遇到一個難題 有一個 **AngularJs 的Webpage** 不知道怎樣砌。。

因為一按那個A tag 的 tab 便轉了去另一個URL  
想了一會便想到有可以嘗試把 &#8220;**A**&#8221; tag &#8220;**HREF**&#8221; tag 的 動作停用。。看看有什麼效果

那麼怎樣才可以  
**解決方法**十分簡單

我們只需要在 A tag 的 tag 內加入 <span style="color: #0000ff;"><strong>onclick=&#8221;return false&#8221;</strong></span>

這個J**avaScript action**便可以了

<pre>&lt;a href="//blog.sharechiwai.com" onclick="return false"&gt; Blog &lt;/a&gt;
</pre>

Hope you find it useful