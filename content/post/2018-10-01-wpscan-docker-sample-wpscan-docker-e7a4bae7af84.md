---
id: 4064
title: 'WPScan Docker Sample &#8211; WPScan Docker 示範'
date: 2018-10-01T09:06:35+08:00
author: ShareChiWai
layout: post
guid: https://blog.sharechiwai.com/?p=4064
permalink: '/2018/10/wpscan-docker-sample-wpscan-docker-%e7%a4%ba%e7%af%84/'
categories:
  - Docker
tags:
  - Docker
  - Security
  - Wordpress
  - WP
  - WPScan
---
如果不想在電腦上安裝 **WPScan** 的話可以考慮使用Docker  
使用方法十分簡單  
首先要 **pull wpscan** 既 **docker image**  
<https://hub.docker.com/r/wpscanteam/wpscan/>

<pre>docker pull wpscanteam/wpscan
</pre>

之後便可以使用這個**Docker image** 來執行 **wpscan** 的指令  
e.g.

<pre>docker run --rm wpscanteam/wpscan --url https://blog.sharechiwai.com
</pre>

如果想直接進入這個wpscan 的docker image 上執行wpscan 可以使用以下指令

<pre>docker run -it --entrypoint /bin/sh wpscanteam/wpscan
</pre>

想了解更多的**wpscan** 的用法可以參考他們的網站  
<https://github.com/wpscanteam/wpscan>

Hope you find it useful