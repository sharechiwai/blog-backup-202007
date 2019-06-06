---
id: 3844
title: 'Cannot read property &#8216;mtime&#8217; of undefined &#8211; Jasmine'
date: 2017-02-22T00:00:53+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3844
permalink: /2017/02/cannot-read-property-mtime-of-undefined-jasmine/
categories:
  - Javascript
---
終於開始做 **Unit Testing** 了  
但是不知道為什麼在自己電腦上Run Unit Test 出現以下的錯誤信息

<span style="color: #008000;"><strong>&#8216;<span style="color: #ff0000;">Running &#8220;connect:test&#8221; (connect) task</span></strong></span>  
<span style="color: #ff0000;"><strong> Started connect web server on http://localhost:9001</strong></span>

<span style="color: #ff0000;"><strong>Running &#8220;karma:unit&#8221; (karma) task</strong></span>  
<span style="color: #ff0000;"><strong> Warning: Cannot read property &#8216;mtime&#8217; of undefined Use &#8211;force to continue.</strong></span>

<span style="color: #008000;"><strong><span style="color: #ff0000;">Aborted due to warnings.</span>&#8216;</strong></span>

[<img class="alignnone size-full wp-image-3846" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png?resize=625%2C119" alt="mtime of undefined" width="625" height="119" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png?w=836 836w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png?resize=300%2C57 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png?resize=768%2C146 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png?resize=624%2C119 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/mtime-of-undefined-cause-by-mklink.png)

最後發現原因可能是 Windows 10 使用 [mklink](https://technet.microsoft.com/en-us/library/cc753194(v=ws.11).aspx)  **symbolic link** 來reference 資料夾/ 檔案的問題  
或是可以bower package version mismatch的問題  
解決方法 就是在Windows上使用傳統的方法  
copy and paste 來複製在Unit Test用到的檔案到要用的資料夾內

之後再進行**Unit test** 便可以解決這個問題了

Hope you find it useful