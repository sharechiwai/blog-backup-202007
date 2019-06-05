---
id: 3566
title: Symfony how to get base URL
date: 2016-02-01T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3566
permalink: /2016/02/symfony-how-to-get-base-url/
categories:
  - Symfony 筆記
tags:
  - Codeigniter
  - Symfony
---
最近由**Codeigniter**轉了使用 **Symfony**..  
有很多概念和coding的功能都不太熟悉..  
有點掛念 **Codeigniter**..  
今天需要用到 **base url 的功能**  
在**Codeigniter** 我們可以使用

<pre>base_url()
</pre>

**解決方法:**  
要取得**Application**的 **base URL**

在**Symfony**我們便可以使用以下的方法

<pre>$this-&gt;request-&gt;getSchemeAndHttpHost()
</pre>

Hope you find it useful