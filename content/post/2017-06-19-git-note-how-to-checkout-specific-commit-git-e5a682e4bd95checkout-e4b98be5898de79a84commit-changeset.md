---
id: 3990
title: 'Git note &#8211; How to checkout specific commit &#8211; Git 如何checkout 之前的Commit / Changeset'
date: 2017-06-19T07:12:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3990
permalink: '/2017/06/git-note-how-to-checkout-specific-commit-git-%e5%a6%82%e4%bd%95checkout-%e4%b9%8b%e5%89%8d%e7%9a%84commit-changeset/'
categories:
  - Git
tags:
  - Git
  - Git Command
  - Git Tips and Tricks
---
常常很大意地 **merge**完一些程式碼後沒有測試便**Commit** 和**Pull** 了到 Remote Repo  
所以便要用 一些 git command 來還原之前的Commit 再去解決問題

那麼如何 還原或 **Checkout** 之前的**Commit** 呢?

**解決方法**分簡單  
我們只需要找到之前**commit**的 hash id 之後 &#8220;<span style="color: #008000;"><strong>git checkout [commit hash]</strong></span>&#8221; 便可以了

查看之前的**Commit** 可以使用 &#8220;<span style="color: #008000;"><strong>git log</strong></span> [<span style="color: #008000;"><strong>-(前多小個commit)</strong></span>]&#8221;  
e.g.

<pre>// 這個指令會輸出前三個commit的資訊
git log -3
</pre>

[<img class="alignnone size-large wp-image-3991" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?resize=625%2C169" alt="Git Log" width="625" height="169" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?resize=1024%2C277 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?resize=300%2C81 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?resize=768%2C208 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?resize=624%2C169 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?w=1580 1580w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/gitlog.png)  
取後**commit hash** 之後 只要輸內前8個以上的characters 應該便足夠令 **git** 識出那個**commit**你想**checkout**的  
之後可以**checkout** 這個commit 了

<pre>git checkout 7aef7c3f
</pre>

**Local Repos** 的 程式碼應該會還原到這個**commit** 時的 程式碼

hope you find it useful