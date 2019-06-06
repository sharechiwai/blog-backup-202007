---
id: 4039
title: Git refusing to merge unrelated histories
date: 2017-12-12T10:11:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4039
permalink: /2017/12/git-refusing-to-merge-unrelated-histories/
categories:
  - Git
tags:
  - Git
  - Git Command
  - Git Tips and Tricks
  - Git Troubleshooting
---
今日剛在**Bitbucket** 建立左一個新既repos  
當我嘗試push local的一個 **git repos**上去既時候出現了以下的錯誤信息  
(當我嘗試Pull這個repos去local的repos時)  
&#8220;<span style="color: #ff0000;"><strong>fatal: refusing to merge unrelated histories</strong></span>&#8221;  
[<img class="alignnone size-large wp-image-4040" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?resize=625%2C294" alt="git Refusing To Merge Unrelated Histories" width="625" height="294" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?resize=1024%2C481 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?resize=300%2C141 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?resize=768%2C361 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?resize=624%2C293 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png?w=1195 1195w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/12/refusingToMergeUnrelatedHistories.png)

如果了解自己的repos 和在 **git**/**bitbucket**上的沒有衝突的話  
**解決方法分簡單**  
我們只需要輸入以卜**git** 指令便可以

<pre>git pull --allow-unrelated-histories
</pre>

Hope you find it useful