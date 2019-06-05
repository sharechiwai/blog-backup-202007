---
id: 3702
title: 'NodeJS &#8211; ejs reference to root path &#8211; HTML reference to root Path for the JS/CSS/Image File'
date: 2016-07-26T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3702
permalink: /2016/07/nodejs-ejs-reference-to-root-path-html-reference-to-root-path-for-the-jscssimage-file/
categories:
  - NodeJs
tags:
  - EJS
  - NodeJs
  - NodeJs Express
---
HTML reference to root Path for the JS/CSS/Image File  
今天在學習**NodeJS with Express** 又遇到問題了  
就是不知道怎樣可以reference 返D **Javascript** /**CSS** 檔案到 **Root Path/ Root Directory**  
之前用 **Codeigniter** 可以使用 **base_url()**  
**ASP.Net MVC** 可以用

<pre>@Styles.Render("~/Content/css")
@Scripts.Render("~/bundles/jquery")
</pre>

當我使用路徑&#8221;**css/bootstrap.min.css**&#8220;.. 在其他的path 便出現問題  
<pre>  
<span style="color: #008000;"><link rel=&#8221;apple-touch-icon&#8221; href=&#8221;apple-touch-icon.png&#8221;></span>

<span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;css/bootstrap.min.css&#8221;></span>  
 <span style="color: #008000;"><style></span>  
 <span style="color: #008000;">body {</span>  
 <span style="color: #008000;">padding-top: 50px;</span>  
 <span style="color: #008000;">padding-bottom: 20px;</span>  
 <span style="color: #008000;">}</span>

<span style="color: #008000;"></style></span>  
 <span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;lib/bootstrap/dist/css/bootstrap-theme.min.css&#8221;/></span>  
 <span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;css/main.css&#8221;></span>  
 <span style="color: #008000;"><script src=&#8221;lib/jquery/dist/jquery.js&#8221;></script></span>  
 <span style="color: #008000;"><script src=&#8221;lib/bootstrap/dist/js/bootstrap.min.js&#8221;></script></span>  
</pre>  
**解決方法**十分簡單..  
只要在 路徑開頭加上 &#8220;/&#8221; 便可以了  
e.g.  
&#8220;/**css/bootstrap.min.css**&#8221;

<pre>  
<span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;/css/bootstrap.min.css&#8221;></span>  
 <span style="color: #008000;"><style></span>  
 <span style="color: #008000;">body {</span>  
 <span style="color: #008000;">padding-top: 50px;</span>  
 <span style="color: #008000;">padding-bottom: 20px;</span>  
 <span style="color: #008000;">}</span>

<span style="color: #008000;"></style></span>  
 <span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;/lib/bootstrap/dist/css/bootstrap-theme.min.css&#8221;/></span>  
 <span style="color: #008000;"><link rel=&#8221;stylesheet&#8221; href=&#8221;/css/main.css&#8221;></span>  
 <span style="color: #008000;"><script src=&#8221;/lib/jquery/dist/jquery.js&#8221;></script></span>  
 <span style="color: #008000;"><script src=&#8221;/lib/bootstrap/dist/js/bootstrap.min.js&#8221;></script></span>  
</pre>

hope you find it useful  
如果有更好的解決方法..希望你可以和大家分享