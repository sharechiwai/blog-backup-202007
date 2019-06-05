---
id: 3874
title: 'fetch origin error: cannot lock ref &#8211; Another git process seems to be running in this repository, e.g. an editor opened by &#8216;git commit&#8217;. Please make sure all processes are terminated then try again. If it still fails, a git process may have crashed in this repository earlier'
date: 2017-02-19T09:05:39+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3874
permalink: /2017/02/fetch-origin-error-cannot-lock-ref-another-git-process-seems-to-be-running-in-this-repository-e-g-an-editor-opened-by-git-commit-please-make-sure-all-processes-are-terminated-then-try-again/
categories:
  - Git
tags:
  - Git
  - Git Troubleshooting
  - Source Control
  - SourceTree
---
今日很䌓忙時候 我的**Git** / **Source Tree** 出現了以下的錯誤信息  
可能是開了太多的**Project** 和 **Local Branch** 的關係

[<img class="alignnone size-full wp-image-3875" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png?resize=625%2C157" alt="Another git process seems to be running in this repository" width="625" height="157" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png?w=821 821w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png?resize=300%2C75 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png?resize=768%2C193 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png?resize=624%2C157 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/lock-git.png)

&#8220;<span style="color: #ff0000;"><strong>git -c diff.mnemonicprefix=false -c core.quotepath=false fetch origin</strong></span>  
<span style="color: #ff0000;"><strong> error: cannot lock ref &#8216;refs/remotes/origin/develop&#8217;: Unable to create &#8216;D:/Git/client-web/.git/refs/remotes/origin/develop.lock&#8217;: File exists.</strong></span>

<span style="color: #ff0000;"><strong>Another git process seems to be running in this repository, e.g.</strong></span>  
<span style="color: #ff0000;"><strong> an editor opened by &#8216;git commit&#8217;. Please make sure all processes</strong></span>  
<span style="color: #ff0000;"><strong> are terminated then try again. If it still fails, a git process</strong></span>  
<span style="color: #ff0000;"><strong> may have crashed in this repository earlier:</strong></span>  
<span style="color: #ff0000;"><strong> remove the file manually to continue.&#8221;</strong></span>

**解決方法**十分簡單  
我們只需要到這個Project 的 &#8220;.Git&#8221; 資料夾內  
e.g.&#8221;**/.git/refs/remotes/origin/**&#8221;

或出那個有 &#8220;.lock&#8221; Extension 的檔案.之後把他&#8221;刪除&#8221; 便可以了

Hope you find it useful