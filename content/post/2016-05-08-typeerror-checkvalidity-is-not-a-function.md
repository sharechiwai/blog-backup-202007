---
id: 3657
title: 'TypeError: $(&#8230;).checkValidity is not a function'
date: 2016-05-08T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3657
permalink: /2016/05/typeerror-checkvalidity-is-not-a-function/
categories:
  - Jquery Notes
tags:
  - HTML5
  - Jquery
  - Jquery Troubleshooting
---
很多時候我們都會使用到一些**custom 的Validation**  
但是我們亦都希望使用**HTML5** 的 **Form Validation** 來做第一線的  
當我嘗試使用 **checkValidity()** 功能時  
**Google Chrome Console**出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>TypeError: $(&#8230;).checkValidity is not a function</strong></span>&#8221;  
做了一會research 之後終於找到解決方法了

<pre>if ($("#frmConfirm").checkValidity()) {
  console.log("Valid");
}
</pre>

**解決方法**:  
**$(&#8220;#frmConfirm&#8221;)[0].checkValidity()**

<pre>if ($("#frmConfirm")[0].checkValidity()) {
  console.log("Valid");
}
</pre>

Hope you find it useful