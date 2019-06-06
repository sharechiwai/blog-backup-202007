---
id: 4149
title: Git Error Unlink of File failed. Should I try again?
date: 2019-04-05T08:48:23+08:00
author: ShareChiWai
layout: post
guid: https://blog.sharechiwai.com/?p=4149
permalink: /2019/04/git-error-unlink-of-file-failed-should-i-try-again/
categories:
  - Git
tags:
  - Git
---
久不久我使用的 Git 便會出現以下問題  
&#8220;**Unlink of file. &#8216; file path and name&#8217; failed. Should I try again? (y/n)**&#8220;<figure class="wp-block-image">

<img src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/image-2.png?w=625&#038;ssl=1" alt="" class="wp-image-4150" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/image-2.png?w=871 871w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/image-2.png?resize=300%2C57 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/image-2.png?resize=768%2C145 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/03/image-2.png?resize=624%2C118 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> </figure> 

很多時候按了 &#8220;Y&#8221; 也是說 file locked &#8230; Should I try again?

**解釋方法**:  
我們只需要執行 git gc command 便可

<pre class="wp-block-preformatted">git gc</pre>

Hope you find it useful