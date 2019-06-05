---
id: 3378
title: 'Codeigniter get user IP address &#8211; 如何使用Codeigniter 取得使用者的IP地址'
date: 2015-01-22T00:00:36+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3378
permalink: '/2015/01/codeigniter-get-user-ip-address-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8codeigniter-%e5%8f%96%e5%be%97%e4%bd%bf%e7%94%a8%e8%80%85%e7%9a%84ip%e5%9c%b0%e5%9d%80/'
categories:
  - Codeingter
tags:
  - PHP
---
之前的網誌和大家介紹了怎樣用PHP 取得 Client IP Address  
<a title="PHP Get Client IP Address on OpenShift" href="http://blog.sharechiwai.com/2013/03/php-get-client-ip-address-on-openshift/" target="_blank">PHP Get Client IP Address on OpenShift</a>

今天想和大家分享當你使用 **Codeigniter Framework**時怎樣取得 **Client IP Address**

**解決方法**十分簡單..  
我們可以直接使用**Codeigniter** 上的 功能 便可以了

<pre>input->ip_address()
</pre>

**E.g.**

<pre>$ip = $this->input->ip_address();
</pre>

Hope you find it useful