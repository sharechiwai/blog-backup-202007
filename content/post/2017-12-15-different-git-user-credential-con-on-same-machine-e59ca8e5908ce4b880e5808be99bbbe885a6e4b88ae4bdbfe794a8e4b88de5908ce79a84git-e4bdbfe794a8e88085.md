---
id: 4044
title: 'Different Git User credential Con on same machine &#8211; 在同一個電腦上使用不同的Git 使用者'
date: 2017-12-15T00:00:17+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4044
permalink: '/2017/12/different-git-user-credential-con-on-same-machine-%e5%9c%a8%e5%90%8c%e4%b8%80%e5%80%8b%e9%9b%bb%e8%85%a6%e4%b8%8a%e4%bd%bf%e7%94%a8%e4%b8%8d%e5%90%8c%e7%9a%84git-%e4%bd%bf%e7%94%a8%e8%80%85/'
categories:
  - Git
tags:
  - Git
  - Git Command
  - Git Tips and Tricks
---
**解決方去**  
我們可以在local的 Git Repos 上設定這個Repos 的**Git Credential**  
我們只需要在 **Git Bash**上輸入以下指令便可以了

<pre>git config user.name "YOUR_USERNAME"

git config user.email "YOUR_EMAIL"
</pre>

如果大家不想每次都要輸入**password** 的話可以輸入以下**Git command** 去 cache你的 **git password**

<pre>git config credential.helper cache
</pre>

Hope you find it useful