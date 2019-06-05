---
id: 3739
title: 'NPM / NodeJs not working on Ubuntu &#8211; NPM / NodeJs沒有反應'
date: 2016-08-12T00:00:30+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3739
permalink: '/2016/08/npm-nodejs-not-working-on-ubuntu-npm-nodejs%e6%b2%92%e6%9c%89%e5%8f%8d%e6%87%89/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - NodeJs
  - Ubuntu
  - Ubuntu Troubleshooting
---
今日嘗試使用 **Node**的時候.發現他**沒有反應**..  
不論我輸入什麼**npm指令**都是沒有輸出任何東西  
[<img class="alignnone size-medium wp-image-3740" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?resize=300%2C49" alt="NPM / Node JS not working, no output" width="300" height="49" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?resize=300%2C49 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?resize=768%2C126 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?resize=1024%2C167 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?resize=624%2C102 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?w=1321 1321w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png?w=1250 1250w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/npmnotworking.png)  
**E.G.**

<pre>npm -v

node -v
</pre>

做了一會research 之後發現應該是我的 **NodeJS Module** Corrupt 了  
解決方法..  
**重新Install NodeJs** 便可以了

<pre>curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
</pre>

[<img class="alignnone size-medium wp-image-3743" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?resize=300%2C113" alt="NodeJs / NPM issue resolved by reinstalling NodeJS" width="300" height="113" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?resize=300%2C113 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?resize=768%2C289 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?resize=1024%2C385 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?resize=624%2C234 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?w=1320 1320w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png?w=1250 1250w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/08/ReinstallNodeJsWorks.png)  
更多安裝**NodeJs**的詳情可以參考以下網頁  
<https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions>

Hope you find it useful