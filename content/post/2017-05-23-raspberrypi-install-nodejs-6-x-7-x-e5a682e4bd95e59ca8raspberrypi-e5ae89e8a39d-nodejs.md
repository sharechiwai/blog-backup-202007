---
id: 3965
title: 'RaspberryPi install NodeJs 6.x / 7.x &#8211; 如何在RaspberryPi 安裝 NodeJs'
date: 2017-05-23T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3965
permalink: '/2017/05/raspberrypi-install-nodejs-6-x-7-x-%e5%a6%82%e4%bd%95%e5%9c%a8raspberrypi-%e5%ae%89%e8%a3%9d-nodejs/'
categories:
  - RaspberryPi
tags:
  - CylonJs
  - Johnny-Five
  - NodeJs
  - RaspberryPi
  - RaspberryPi setup
---
今日嘗試在**RaspberryPi**上安裝**Johnny-Five** /**CylonJs** 時出現**NodeJs** 的版本問題  
但是執行

<pre>sudo apt-get install node
</pre>

他說 **NodeJs**已經安裝了

做了一會research 之後 發現我們可以使用以下方法來更新這個**NodeJs**的

**解決方法**  
我𠍒可以在**Terminal** 上執行以下**command**  
**NodeJs 6.x**

<pre>curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
</pre>

**NodeJs 7.x**

<pre>curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
</pre>

[<img class="alignnone size-large wp-image-3967" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?resize=625%2C370" alt="Install NodeJs on RaspberryPi" width="625" height="370" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?resize=1024%2C607 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?resize=300%2C178 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?resize=768%2C455 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?resize=624%2C370 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?w=1318 1318w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/04/InstallNodeJsRaspberry.png)

完成後再次執行

<pre>sudo apt-get install node
</pre>

詳情可以參考以下網頁  
<https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions>

Hope you find it useful