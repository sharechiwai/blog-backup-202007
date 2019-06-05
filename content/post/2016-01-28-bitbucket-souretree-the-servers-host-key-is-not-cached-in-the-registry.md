---
id: 3562
title: 'BitBucket SoureTree &#8211; The server&#8217;s host key is not cached in the registry'
date: 2016-01-28T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3562
permalink: /2016/01/bitbucket-souretree-the-servers-host-key-is-not-cached-in-the-registry/
categories:
  - Git
tags:
  - BitBucket
  - Git
  - Source Control
  - SourceTree
---
今天嘗試使用**SourceTree** 去 **Push**一個新的**Git Repos**  
誰不知 **Push**了很久都是停留在同一個**output Windows**上  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1649/24724041236_73170373b2_z.jpg?resize=625%2C384" alt="SourceTree Output Windows - The server's host key is not cached in the registry" width="625" height="384" data-recalc-dims="1" /> 

<pre>git -c diff.mnemonicprefix=false -c core.quotepath=false push -v --tags --set-upstream origin master:master
Pushing to git@bitbucket.org:sharechiwai/SampleCode.git

The server's host key is not cached in the registry. You
have no guarantee that the server is the computer you
think it is.
The server's rsa2 key fingerprint is:
ssh-rsa 2048 97:xxxxxxxxxxxxxxxxxxxxxxx
If you trust this host, enter "y" to add the key to
PuTTY's cache and carry on connecting.

If you want to carry on connecting just once, without
adding the key to the cache, enter "n".
If you do not trust this host, press Return to abandon the
connection.</pre>

做了一會research之後終於找到解決方法了

**解決方法**:  
大家可以使用**Command Prompt**之後輸入以下指令到 **Source tree**的 **Putty資料夾**

<pre>cd "C:\Program Files (x86)\Atlassian\SourceTree\tools\putty"
</pre>

之後執行以下指令到連接到 **BitBucket**

<pre>plink git@bitbucket.org
</pre>

他便會出現上面的問題..叫你把**Host Key Cach**到 **Registry**裡  
<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1507/24750243185_f66a021456_z.jpg?resize=625%2C347" alt="BitBucket SourceTree - The server's host key is not cached in the registry Solutions" width="625" height="347" data-recalc-dims="1" />  
完成後再嘗試使用**Source** Tree 去**Push**  
這一次很快便可以把這一個**Local Repos Push**上了**BitBucket**了

Hope you find it useful