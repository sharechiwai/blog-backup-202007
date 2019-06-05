---
id: 3450
title: 'Codeigniter How to run pre-define SQL function on Codeigniter- 在Codeigniter上如何輸入SQL 預設的功能 E.G. UUID()'
date: 2015-08-03T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3450
permalink: '/2015/08/codeigniter-how-to-run-pre-define-sql-function-on-codeigniter-%e5%9c%a8codeigniter%e4%b8%8a%e5%a6%82%e4%bd%95%e8%bc%b8%e5%85%a5sql-%e9%a0%90%e8%a8%ad%e7%9a%84%e5%8a%9f%e8%83%bd-e-g-uuid/'
categories:
  - Codeingter
tags:
  - Codeigniter
  - HeidiSQL
  - mysql
  - PHP
---
今天嘗試使用**HeidiSQL** 在**MySQL Database**上設計一個Table的其中一個Field 使用**UUID** 來做預設值  
誰不知當我輸入新的Record時他自動化輸入了&#8221;<span style="color: #339966;"><strong>UUID()</strong></span>&#8221; 進這個Field上  
<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/559/19633495914_a1445b165f_z.jpg?resize=462%2C29" alt="UUID() on MySQL Field" width="462" height="29" data-recalc-dims="1" /> 

那麼我便嘗試自行使用**Codeigniter** 的**SQL** 功能來輸入 這個<span style="color: #339966;"><strong>UUID()</strong></span>  
**E.G.**

<pre>$this-&gt;db-&gt;set('my_id', 'UUID()');
</pre>

但是結果也是一樣

做了一會reseach 之後終於找到了解決方法

**解決方法**..  
我們只需要 **db->set**的第三個變數設定成 <span style="color: #ff0000;"><strong>FALSE</strong> </span>便可以  
這個變數是用來定義叫**Codeigniter** 不用**escape** 這個內容

<pre>$this-&gt;db-&gt;set('my_id', 'UUID()', FALSE);
</pre>

Hope you find it useful