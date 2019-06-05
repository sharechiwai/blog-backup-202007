---
id: 3533
title: Linux System update command to update and remove component
date: 2016-01-02T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3533
permalink: /2016/01/linux-system-update-command-to-update-and-remove-component/
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Ubuntu
---
之前和大家分享過一些**Linux Command 來更新Linux 系統**  
**<a href="http://blog.sharechiwai.com/2014/07/how-to-update-ubuntu-linux-system-update-%e5%a6%82%e4%bd%95%e6%9b%b4%e6%96%b0linux-ubuntu/" target="_blank">How to update Ubuntu – Linux System Update – 如何更新Linux [Ubuntu]</a>**

今天發現原來我們可以把所有要用的**Command** 指令寫在同一個Command 裡  
之後一起執行&#8230;這可以減小要等待輸入下一個指令的時間  
只要在有需要下決定的時候選擇 **Yes**繼續執行 或 **No** 放棄執行便可以  
十分方便

這個指令是這樣子的

<pre>sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get autoremove
</pre>

  1. 他會執行更新 **Update information**
  2. 之後更新系統..
  3. 最後會移除沒有用的元件  
    當要使用者下決定時便會停下來等待使用者選擇是否執行  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1483/24232539189_4f82af298d_z.jpg?resize=625%2C370" alt="Linux System Update ask if user want to process" width="625" height="370" data-recalc-dims="1" /> 

Hope you find it useful