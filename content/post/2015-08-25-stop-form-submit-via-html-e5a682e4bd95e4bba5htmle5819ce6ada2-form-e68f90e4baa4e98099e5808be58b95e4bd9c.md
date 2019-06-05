---
id: 3474
title: 'Stop form submit via HTML &#8211; 如何以HTML停止 Form 提交這個動作'
date: 2015-08-25T00:00:38+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3474
permalink: '/2015/08/stop-form-submit-via-html-%e5%a6%82%e4%bd%95%e4%bb%a5html%e5%81%9c%e6%ad%a2-form-%e6%8f%90%e4%ba%a4%e9%80%99%e5%80%8b%e5%8b%95%e4%bd%9c/'
categories:
  - HTML/CSS
tags:
  - HTML
  - HTML5
  - Javascript
---
最近想做一些**demo**的**page**來試一些**Javascript** 的程式碼  
之後發現 任何 **button** 在 **form tag** 之後  
當你按下時..他便會做出　**Form Submit**這個動作  
**e.g. 以下的例子會做出Form Submit這個動作**

<form role=&#8221;form&#8221; id=&#8221;frmWontSubmit&#8221; action=&#8221;http://blog.sharechiwai.com&#8221; >  
<button onclick=&#8221;alert(&#8216;Hello&#8217;);&#8221;> Say Hello</button>  
</form>

**解決方法**十分簡單

我們只需要在 **HTML** 的 **Form tag**上加上 <span style="color: #339966;"><strong>onSubmit=&#8221;return false&#8221;</strong> </span>便可以  
E.G.

<form role=&#8221;form&#8221; id=&#8221;frmWontSubmit&#8221; action=&#8221;http://blog.sharechiwai.com&#8221; onSubmit=&#8221;return false;&#8221;>  
<button onclick=&#8221;alert(&#8216;Hello&#8217;);&#8221;> Say Hello</button>  
</form>

**<a href="http://sharechiwai.com/demo/html/disable_form_submit" target="_blank">Demo</a>**

<img class="alignnone" src="https://i1.wp.com/farm1.static.flickr.com/370/20207042138_5210eb3867_z.jpg?resize=625%2C233" alt="HTML5 Form Submit  Demo" width="625" height="233" data-recalc-dims="1" /> 

Hope you find it useful