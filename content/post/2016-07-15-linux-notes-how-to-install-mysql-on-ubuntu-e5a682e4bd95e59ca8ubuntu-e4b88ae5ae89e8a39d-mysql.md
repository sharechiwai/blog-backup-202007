---
id: 3749
title: 'Linux Notes &#8211; How to install MySQL on Ubuntu &#8211; 如何在Ubuntu 上安裝 MySQL'
date: 2016-07-15T00:00:54+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3749
permalink: '/2016/07/linux-notes-how-to-install-mysql-on-ubuntu-%e5%a6%82%e4%bd%95%e5%9c%a8ubuntu-%e4%b8%8a%e5%ae%89%e8%a3%9d-mysql/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - mysql
  - Ubuntu
  - Ubuntu Settings
---
最近常常在練習**安裝**/**設定 Ubuntu Linux**  
用作Host **Web Application** 的 **Web Server**.  
很多時候都會用以下是**Ubuntu** 安裝** MySQL Server** 的Command

<pre>sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
sudo mysql_install_db
</pre>

安裝完成後可以執行以下的指令去**進階設定MySQL 令他更安全**

<pre>sudo mysql_secure_installation
</pre>

Hope you find it useful