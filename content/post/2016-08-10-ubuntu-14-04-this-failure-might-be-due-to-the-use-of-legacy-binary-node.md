---
id: 3732
title: 'Ubuntu 14.04 &#8211; This failure might be due to the use of legacy binary &#8220;node&#8221;'
date: 2016-08-10T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3732
permalink: /2016/08/ubuntu-14-04-this-failure-might-be-due-to-the-use-of-legacy-binary-node/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Asp.net core
  - Linux
  - Npm
  - Ubuntu
  - Ubuntu Troubleshooting
  - Yemon
---
今日嘗試在**Ubuntu** 安裝**Yemon** 去在**Ubuntu Server 14.04** 上測試  
**Asp.net Core**的 setup

<pre>sudo npm install -g yo
</pre>

但是出現了以下的**錯誤信息**  
&#8220;<span style="color: #ff0000;"><strong>This failure might be due to the use of legacy binary &#8216;node&#8217;</strong></span>&#8221;  
[<img class="alignnone wp-image-3734 size-medium" title="This failure might be due to the use of legacy binary &quot;node&quot;" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?resize=300%2C107" alt="This failure might be due to the use of legacy binary &quot;node&quot;" width="300" height="107" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?resize=300%2C107 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?resize=768%2C275 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?resize=1024%2C367 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?resize=624%2C223 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?w=1355 1355w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png?w=1250 1250w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/LegacyBinaryNode.png)  
做完一會research之後發現現來是 **Ubuntu 14.04**的問題  
他的**node** 是用 **nodejs**來執行的

**解決方法** 十分簡單..我們只需要建立一個**symbolink** 來把 **node** 和 **nodejs** 連接在一起..  
令到在執行 **node**時..實際是在執行 **nodejs**..便可以了

<pre>sudo ln -s /usr/bin/nodejs /usr/bin/node
</pre>

Hope you find it useful