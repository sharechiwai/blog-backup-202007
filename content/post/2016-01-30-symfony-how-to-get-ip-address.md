---
id: 3564
title: Symfony how to get ip address
date: 2016-01-30T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3564
permalink: /2016/01/symfony-how-to-get-ip-address/
categories:
  - Symfony 筆記
tags:
  - Symfony
---
很多時候都會用到的一個**PHP** 功能  
如何在**Symfony**上取得使用者 **IP Address**  
大家可以使用這個方法

<pre>$this-&gt;container-&gt;get('request')-&gt;getClientIp();
</pre>

Hope you find it useful