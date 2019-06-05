---
id: 2987
title: 'TypeError: Object [object Object] has no method &#8216;live&#8217;'
date: 2014-01-10T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2987
permalink: /2014/01/typeerror-object-object-object-has-no-method-live/
categories:
  - Jquery Notes
tags:
  - Jquery
---
今天公司的網頁其中某些功能出現了問題  
用戶**Click** 了之後沒有反應&#8230;  
在**Google Chrome Developer Tools Console** 上找到以下的錯誤信息  
&#8220;**<span style="color: #ff0000;">TypeError: Object [object Object] has no method &#8216;live&#8217;</span>**&#8221;

做了research之後發現&#8230;  
原來是同事更新了 網頁上的**JQuery** 版本.. 從  
**JQuery 1.7.2** 更新到 **JQuery 1.10.2**  
**在JQuery 1.9**的時候 已經不再支援 **.live()** 這個功能了

**解決方法..**  
**解決方法** 一:  
這個方法比較簡單..  
只是我做在頁面上加入  
以下的JQuery Migrate Javascript 檔案便可以了  
<a title="JQuery Migrate Javascript" href="http://code.jquery.com/jquery-migrate-1.2.1.js" target="_blank">http://code.jquery.com/jquery-migrate-1.2.1.js</a>

或到以下網址下載更新的 file

<a title="JQuery Download" href="http://jquery.com/download/" target="_blank">http://jquery.com/download/</a>

解決方法 **二**:  
更好的方法是看看自己的程式碼..  
把 &#8220;**.live()**&#8221; 這個已經 **deprecate** 的 method  
轉成 &#8220;**.on()**&#8221; 便可以了

Hope you find it useful