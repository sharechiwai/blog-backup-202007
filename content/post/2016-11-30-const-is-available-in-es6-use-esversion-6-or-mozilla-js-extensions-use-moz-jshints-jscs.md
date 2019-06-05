---
id: 3768
title: '&#8216;const&#8217; is available in ES6 (use &#8216;esversion: 6&#8217;) or Mozilla JS extensions (use moz). JSHints JSCS'
date: 2016-11-30T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3768
permalink: /2016/11/const-is-available-in-es6-use-esversion-6-or-mozilla-js-extensions-use-moz-jshints-jscs/
categories:
  - Javascript
---
搭飛機訓唔著係一件十分痛苦的事..  
幸好..可以給我一些時間去tidy up自己之前hackathon 的Code  
但在執行gulp 的**JSCS** 時出現以下的Warning.

&#8220;<span style="color: #ff0000;"><strong>&#8216;const&#8217; is available in ES6 (use &#8216;esversion: 6&#8217;) or Mozilla JS extensions (use moz).</strong></span>&#8221;  
[<img class="alignnone size-large wp-image-3770" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?resize=625%2C110" alt="'const' is available in ES6 (use 'esversion: 6') or Mozilla JS extensions (use moz)" width="625" height="110" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?resize=1024%2C180 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?resize=300%2C53 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?resize=768%2C135 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?resize=624%2C110 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/isavaliableInES6.png)

在機上不能上網..今天終於有時間去research下怎樣解決

**解決方法**十分簡單..  
只要在 **.js** 檔案的上方 加入下**comment**便可以不再顯示這些Warning  
<img class="alignnone size-full wp-image-3771" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/esversion6.png?resize=625%2C119" alt="jshints esversion 6 issue fixed" width="625" height="119" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/esversion6.png?w=689 689w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/esversion6.png?resize=300%2C57 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/11/esversion6.png?resize=624%2C119 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> 

<pre>/*jshint esversion: 6 */
</pre>

Hope you find it useful