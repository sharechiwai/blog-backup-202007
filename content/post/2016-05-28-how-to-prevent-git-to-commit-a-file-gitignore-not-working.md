---
id: 3683
title: How to prevent git to commit a file, .gitignore not working
date: 2016-05-28T00:00:09+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3683
permalink: /2016/05/how-to-prevent-git-to-commit-a-file-gitignore-not-working/
categories:
  - Git
tags:
  - Git
  - Git Troubleshooting
  - GitHub
  - Open source
---
之前的網誌介紹了我把學習 **NodeJs**的程式碼 **Open source**了到 **GitHub**上  
<https://github.com/sharechiwai/NodeExpress>  
現在發現有小小的難題..  
就是很多的**Web Application** 都有使用**第三方的API**  
如果直接把那些 **API Key**都 **Commit** 到**GitHub**上那便會所有人都能我申請的 **API Key** 了  
不太安全吧..  
所以我便做了很多research看看怎樣解決這個問題.  
很多網友都說只要修改 **.gitignore** 加上那個不想**commit**的檔案路俓便可以了  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7095/26586779044_97fdba0c55_z.jpg?resize=625%2C395" alt=".gitignore config" width="625" height="395" data-recalc-dims="1" />  
但是試了很久也不成功 在**GitHub Application**上還是可以看到 那個**config.js  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7793/27159606086_e81961f06f_z.jpg?resize=625%2C343" alt="config.js still showing on github to be commit" width="625" height="343" data-recalc-dims="1" />  
** 

最後終於找到了為什麼 **.gitignore** not working 和**解決方法**了

加了檔案路徑到**.gitignore** 都不能解決  
是因為**.gitignore** 只能處理**untrack**的檔案..  
即是如果你的檔案之前 **commit**過.當那個檔案有任何改變是Git都會說有檔案可以**commit</p> 

</strong>

**解決方法**..  
我們需要使用 **command prompt** 在這個**Git的 repository** 上輸入以下的指令  
<span style="color: #339966;"><strong>git update-index &#8211;assume-unchanged</strong></span> [<span style="color: #3366ff;"><strong>File path / 檔案路徑/ 如果只有指定檔案, 可以加檔案名/ 否則便會整個資料夾都不會 commit</strong></span>]

e.g.

<pre>git update-index --assume-unchanged config/config.js
</pre>

<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7595/27097109522_51d68ea19b_z.jpg?resize=625%2C117" alt="Git command to make git treat the specific file/folder unchanged" width="625" height="117" data-recalc-dims="1" />  
得左  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7726/27097109702_bb87956c1a_z.jpg?resize=625%2C380" alt="config.js not showing on git application" width="625" height="380" data-recalc-dims="1" /> 

有時候大家想**Git**再次**commit**這個檔案..可以在**command prompt**上使用這個指令  
<span style="color: #008000;"><strong>git update-index &#8211;no-assume-unchanged</strong></span> [<span style="color: #3366ff;"><strong>File path / 檔案路徑/ 如果只有指定檔案, 可以加檔案名/ 否則便會整個資料夾都不會 commit</strong></span>]

E.G.

<pre>git update-index --no-assume-unchanged config/config.js
</pre>

<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7595/27097109522_51d68ea19b_z.jpg?resize=625%2C117" alt="Git command to ensure the file/folder are tracked" width="625" height="117" data-recalc-dims="1" />  
Hope you find it useful