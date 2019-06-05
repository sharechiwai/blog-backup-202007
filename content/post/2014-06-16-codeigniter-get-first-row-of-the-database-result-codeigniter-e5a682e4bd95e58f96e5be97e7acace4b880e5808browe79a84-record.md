---
id: 3235
title: 'Codeigniter Get first Row of the database result &#8211; Codeigniter 如何取得第一個Row的 Record'
date: 2014-06-16T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3235
permalink: '/2014/06/codeigniter-get-first-row-of-the-database-result-codeigniter-%e5%a6%82%e4%bd%95%e5%8f%96%e5%be%97%e7%ac%ac%e4%b8%80%e5%80%8brow%e7%9a%84-record/'
categories:
  - Codeingter
tags:
  - PHP
---
今天在電腦活動 **Hackathon** 上寫一些**Web Service**用來 在Server 上的Database  
取一些資了  
誰不知..我忘了怎樣可以簡單地使用**Codeigniter** 的**Active Record**來取得第一個Record  
所以便想寫下今天的網誌作一個小小的筆記了

**解決方法** 十分簡單  
我們可以使用 <span style="color: #008000;"><strong>$row = query->row()</strong></span>便可以  
E.G.

<pre>if($query->num_rows() > 0){
  // Get current row
  $row = $query->row();
}

</pre>

<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3917/14727867003_4039e7ced1_z.jpg?resize=283%2C76" alt="Codeigniter Get Current Records" width="283" height="76" data-recalc-dims="1" /> 

Hope you find it useful