---
id: 3659
title: 'HTML5 Input type=number do not accept decimal number &#8211; HTML5 Input type number 不能輸入小數位'
date: 2016-05-10T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3659
permalink: '/2016/05/html5-input-typenumber-do-not-accept-decimal-number-html5-input-type-number-%e4%b8%8d%e8%83%bd%e8%bc%b8%e5%85%a5%e5%b0%8f%e6%95%b8%e4%bd%8d/'
categories:
  - HTML/CSS
tags:
  - HTML5
---
在公司的Web project上.. 希可以可好好運用**HTML5** 的 input type 上的**Form Validation**  
這可以增加 data input的安全度

誰不知.. 當我在 **input type=&#8221;number&#8221;** 的 text**b**ox上輸入有小數的數值時  
他出現錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Please enter a valid value, The two nearest value are</strong> </span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7661/26577559270_02309f9792_z.jpg?resize=426%2C134" alt="Please enter a valid value" width="426" height="134" data-recalc-dims="1" /> 

<pre>&lt;form&gt;
&lt;label&gt; Amount
&lt;input type="number"/&gt;
&lt;/label&gt;
&lt;/form&gt;</pre>

**解決放法**  
我們只需要在這個 type=&#8221;number&#8221;的 input tag 上加上 step=&#8221;any&#8221; 這個屬性便可以了  
**<span style="color: #008000;"><input type=&#8221;number&#8221; step=&#8221;any&#8221; /></span>**

E.g.

<pre>&lt;form&gt;
&lt;label&gt; Amount
&lt;input type="number" step="any"/&gt;
&lt;/label&gt;
&lt;/form&gt;</pre>

Hope you find it useful