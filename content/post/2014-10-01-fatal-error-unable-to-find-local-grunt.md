---
id: 3320
title: 'Fatal error: Unable to find local grunt'
date: 2014-10-01T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3320
permalink: /2014/10/fatal-error-unable-to-find-local-grunt/
categories:
  - Grunt
---
今天朋友幫我的一個網頁升級了使用**Grunt**來**Automate** 一些Task  
E.g. **Minify CSS** / **JS** 等等.. 有時間會在大家分享使用**GruntJS** 的好處  
<a title="Grunt: The Javascript Task Runner" href="http://gruntjs.com/" target="_blank">http://gruntjs.com/</a>

當我嘗試使用**Grunt**的時候出現了這個錯誤信息&#8230;

&#8220;**<span style="color: #ff0000;">Fatal error: Unable to find local grunt.</span>**&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3893/15388610895_d551ca65c4_z.jpg?resize=625%2C281" alt="Fatal error: Unable to find local grunt," width="625" height="281" data-recalc-dims="1" />  
&#8221;  
**<span style="color: #ff0000;">grunt-cli: The grunt command line interface. (v0.1.13)</span>**

**<span style="color: #ff0000;">Fatal error: Unable to find local grunt.</span>**

**<span style="color: #ff0000;">If you&#8217;re seeing this message, either a Gruntfile wasn&#8217;t found or grunt</span>**  
** <span style="color: #ff0000;">hasn&#8217;t been installed locally to your project. For more information about</span>**  
** <span style="color: #ff0000;">installing and configuring grunt, please see the Getting Started guide:</span>**

<a title="Grunt: The Javascript Task Runner" href="http://gruntjs.com/getting-started" target="_blank">http://gruntjs.com/getting-started</a>  
&#8221;

記得自己的電腦上已經安裝了Grunt 而他的錯誤信息也說明 安裝在電腦上的版本名稱  
&#8220;**grunt-cli: The grunt command line interface. (v0.1.13)**&#8221;

為什麼還是找不到呢..

做了一會Research之後發現..原來需要在每一個Project 的資料夾上 都要安裝一次的

**解決方法**

我們可以在這個**Project**上的**Root**資料夾執行下以指令

<pre>npm install grunt --save-dev
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3852/15201941160_a00b2a1f32_z.jpg?resize=625%2C511" alt="Install GruntJS" width="625" height="511" data-recalc-dims="1" /> 

在這個資料夾內安裝了**Grunt** [**Local 的 Grunt**]  
便可以執行**Grunt**了

建議在安裝完**Grunt**之後要耐執行以下指令..

<pre>npm install
</pre>

用來更新這個**Grunt**/**Project**的 **Dependence**  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2948/15385442951_ecf8bc853e_z.jpg?resize=625%2C313" alt="npm Install -> to install missing dependency " width="625" height="313" data-recalc-dims="1" /> 

安裝完成後便可以再次執行 **Grunt**了

<pre>Grunt
</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3874/15388300862_7cc1746088_z.jpg?resize=555%2C261" alt="GruntJs is running" width="555" height="261" data-recalc-dims="1" /> Grunt

Hope you find it useful