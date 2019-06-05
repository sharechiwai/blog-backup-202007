---
id: 4015
title: 'How to use &#038;&#038; (bash) in powershell to run multiple command'
date: 2017-07-02T09:32:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4015
permalink: /2017/07/how-to-use-bash-in-powershell-to-run-multiple-command/
categories:
  - Powershell
tags:
  - Bash
  - PowerShell
  - VSCode
---
在這間公司工作..  
我學會了很多command (多數是在 bash [git bash] 上使用的)

回家後可能是因為 screen 比較細的關係  
所以很小會開**git bash** 來執行指令  
會使用**Visual Studio code** instead  
**VS code** 是使用**Powershell**的  
所以當我嘗試執行

<pre>git fetch && git checkout develop
</pre>

遇到以下的錯誤信息  
&#8221;  
<span style="color: #ff0000;"><strong>At line:1 char:12</strong></span>  
<span style="color: #ff0000;"><strong>+ git fetch && git checkout develop</strong></span>  
<span style="color: #ff0000;"><strong>+ ~~</strong></span>  
<span style="color: #ff0000;"><strong>The token &#8216;&&&#8217; is not a valid statement separator in this version.</strong></span>  
<span style="color: #ff0000;"><strong> + CategoryInfo : ParserError: (:) [], ParentContainsErrorRecordException</strong></span>  
<span style="color: #ff0000;"><strong> + FullyQualifiedErrorId : InvalidEndOfLine</strong></span>  
&#8221;  
[<img class="alignnone size-large wp-image-4016" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?resize=625%2C173" alt="try to use && in powershell" width="625" height="173" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?resize=1024%2C284 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?resize=300%2C83 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?resize=768%2C213 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?resize=624%2C173 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?w=1592 1592w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/ampSignOnPowerShell.png)

**解決方法**  
我們只需要把 &#8220;**&&**&#8221; 轉成 &#8220;**;**&#8221; 便可以了

<pre>git fetch ; git checkout develop
</pre>

[<img class="alignnone size-large wp-image-4017" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?resize=625%2C87" alt="&& alternative in powershell" width="625" height="87" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?resize=1024%2C142 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?resize=300%2C42 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?resize=768%2C107 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?resize=624%2C87 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?w=1528 1528w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/semicolonOnPowerShell.png)  
Hope you find it useful