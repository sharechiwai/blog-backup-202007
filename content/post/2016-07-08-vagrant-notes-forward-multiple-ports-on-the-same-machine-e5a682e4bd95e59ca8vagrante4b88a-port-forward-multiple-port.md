---
id: 3730
title: 'Vagrant Notes forward multiple ports on the same machine &#8211; 如何在Vagrant上 Port Forward Multiple Port?'
date: 2016-07-08T00:00:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3730
permalink: '/2016/07/vagrant-notes-forward-multiple-ports-on-the-same-machine-%e5%a6%82%e4%bd%95%e5%9c%a8vagrant%e4%b8%8a-port-forward-multiple-port/'
categories:
  - Vagrant 筆記
tags:
  - Vagrant
  - Vagrant Config
  - Vagrant Settings
---
開始常常用**Vagrant** 來嘗試建立自己的**VPS**  
今日又出現了小小的問題需要上網  
**如何在Vagrant上 Port Forward Multiple Port**呢?

**解決方法**十分簡單&#8230;  
我們只需要在**VagrantFile** 上在不同的**Port forward**上加上以下的**設定**便可以了

<pre># config.vm.network "forwarded_port", guest: [port], host: [port]
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 22, host: 22
</pre>

E.G.

<pre>Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision "shell", path: "provision.sh"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 22, host: 22
end
</pre>

Hope you find it useful