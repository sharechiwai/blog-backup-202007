---
id: 4138
title: 'Linux updated folder and subfolder&#8217;s ownership'
date: 2019-03-11T00:00:18+08:00
author: ShareChiWai
layout: post
guid: https://blog.sharechiwai.com/?p=4138
permalink: /2019/03/linux-updated-folder-and-subfolders-ownership/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux Command
---
只要把這個folder的ownership 轉為 www-data 便可  
我們可以使用 sudo chown user:usergroup folder/*

今日發現自從把wordpress 轉了用docker host 之後便不能 upload file  
原因是我把之wordpress site 的檔案從 FTP upload 到新server 的 uploads folder  
的ownership 是我FTP 的user名 而不是 run wordpress 的www-data

解決放法

<pre class="wp-block-preformatted">sudo chown www-data:www-data uploads/*</pre>

Hope you find it useful