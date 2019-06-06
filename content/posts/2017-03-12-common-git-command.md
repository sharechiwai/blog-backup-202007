---
id: 3803
title: Common Git Command
date: 2017-03-12T00:00:37+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3803
permalink: /2017/03/common-git-command/
categories:
  - Git
tags:
  - BitBucket
  - Git
  - Git Command
  - SourceTree
---
新公司是用**Git** 的  
很多同事都是使用**Git Bash** 來**Commit**/**Pull**/**Push** source 去**Bitbucket**  
由於不太懂**Git command**的關係  
所以我便用**Bitbucket**的**Source Tree**..  
可能是太多**Projects**/ **Repositories**  
久不久..我的**Source Tree** 便出現問題..  
之前還試過

以下是一些常用的 **Git Command**

//用來提取這個**repository** 的最近資料

<pre>git fetch
</pre>

// 用來**checkout branch**

<pre>git checkout [branch name]
</pre>

// 用來**Pull** 最新的 current branch

<pre>git pull 
</pre>

// 加 unstage 的 file

<pre>git add *

// 或一個一個檔案 stage
git add FileToStage
</pre>

// **commit**

<pre>git commit -m "message"
</pre>

//**push**

<pre>git push
</pre>

// **merge the specific branch to current**

<pre>git merge develop
</pre>

這會**merge develop branch** 到**current checkout**的**branch**

暫時分享住這些  
有機會再share 其他常用的**git command**

Hope you find it useful