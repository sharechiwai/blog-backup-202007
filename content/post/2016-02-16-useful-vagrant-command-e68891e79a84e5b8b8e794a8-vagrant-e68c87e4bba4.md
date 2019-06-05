---
id: 3596
title: 'Useful Vagrant Command &#8211; 我的常用 Vagrant 指令'
date: 2016-02-16T00:00:41+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3596
permalink: '/2016/02/useful-vagrant-command-%e6%88%91%e7%9a%84%e5%b8%b8%e7%94%a8-vagrant-%e6%8c%87%e4%bb%a4/'
categories:
  - Vagrant 筆記
---
最近發現 **Vagrant**真是很好用&#8230;我終於成功在 Linux Ubuntu在 執行 ASP.Net website了  
首先當然是在Vagrant上試驗

以下是我最常用的 Vagrant Command

Vagrant Up &#8211; 跟據 Vagrantfile 來建立和設定你的 Virtual Machine

<pre>Vagrant Up
</pre>

vagrant halt &#8211; 用來關閉Virtual Machine的指令.. 當失敗的話..便會使用 &#8211;force [像Power off一樣]的指令

<pre>vagrant halt
</pre>

vagrant destroy &#8211; 用來刪除這個virtual machine的指令, 就像回到Virtual machine未建立的時候

<pre>vagrant destroy
</pre>

vagrant reload &#8211; 重新啟動 virtual machine e.g. vagrant halt + vagrant up 指令一起執行

<pre>vagrant reload
</pre>

vagrant status &#8211; 來檢查virtual machine的 current status e.g. up and running還是沒有啟動

<pre>vagrant status
</pre>

<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1555/24463860544_1feb78638a_z.jpg?resize=625%2C137" alt="Vagrant Status" width="625" height="137" data-recalc-dims="1" />  
**vagrant provision** &#8211; **執行 provision的設定** &#8211; 如果你有一個provision的檔案 便可以運用這個指令再以執行這個provision檔案  
&#8211; 當我研究怎樣在Linux上執行 .net core / ASP.Net 時常常更新 provision 檔案來試指令時常常用到的

<pre>vagrant provision
</pre>

當找到其他常用的指令再更近這個Blog =)

Hope you find it useful